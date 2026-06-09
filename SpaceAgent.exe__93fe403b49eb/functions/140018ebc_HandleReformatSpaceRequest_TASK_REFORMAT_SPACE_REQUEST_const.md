# HandleReformatSpaceRequest(TASK_REFORMAT_SPACE_REQUEST const *)

- ea: `0x140018ebc`
- end: `0x140018fb5`
- name: `?HandleReformatSpaceRequest@@YAHPEBUTASK_REFORMAT_SPACE_REQUEST@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(const struct TASK_REFORMAT_SPACE_REQUEST *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x140017d70`

## callees

- `0x140001caf`
- `0x140012e28`
- `0x140016f48`
- `0x14001832c`
- `0x140018ebc`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140018f7a`
- `KERNEL32!LocalFree` at `0x140018f7a`
- `KERNEL32!SetLastError` at `0x140018f0b`
- `KERNEL32!SetLastError` at `0x140018f98`
- `KERNEL32!SetLastError` at `0x140018f0b`
- `KERNEL32!SetLastError` at `0x140018f98`
- `KERNEL32!GetLastError` at `0x140018f6a`
- `KERNEL32!GetLastError` at `0x140018f8e`
- `KERNEL32!GetLastError` at `0x140018f6a`
- `KERNEL32!GetLastError` at `0x140018f8e`

## pseudocode

```c
__int64 __fastcall HandleReformatSpaceRequest(const struct TASK_REFORMAT_SPACE_REQUEST *a1)
{
  struct _SU_SPACE_OBJECT *v2; // rdi
  unsigned int v3; // ebx
  unsigned int v4; // r8d
  int SpaceFiltered; // eax
  DWORD LastError; // esi
  HLOCAL v7; // rax
  _BYTE v9[40]; // [rsp+20h] [rbp-B58h] BYREF
  __int128 v10; // [rsp+48h] [rbp-B30h]
  unsigned __int16 v11; // [rsp+B88h] [rbp+10h] BYREF
  struct _SU_SPACE_OBJECT *v12; // [rsp+B90h] [rbp+18h] BYREF

  memset_0(v9, 0, 0xB48u);
  v2 = 0;
  v12 = 0;
  v3 = IssueProgressStringResult(32894);
  if ( v3 )
  {
    if ( *(_QWORD *)a1 == 576 )
    {
      v10 = *((_OWORD *)a1 + 1);
      SpaceFiltered = SuGetSpaceFiltered((struct _SU_POOL_OBJECT *)v9, (struct _GUID *)((char *)a1 + 44), v4, &v12);
      v2 = v12;
      v3 = SpaceFiltered;
      if ( SpaceFiltered )
      {
        v11 = *((_WORD *)a1 + 286);
        v3 = SuReformatSpace(v12, (const unsigned __int16 *)a1 + 16, (const unsigned __int16 *)a1 + 30, &v11);
      }
    }
    else
    {
      v3 = 0;
      SetLastError(0x18u);
    }
  }
  LastError = GetLastError();
  if ( v2 )
  {
    v7 = LocalFree(v2);
    if ( v3 )
    {
      v3 = v7 == 0;
      LastError = GetLastError();
    }
  }
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x140018ebc  mov     [rsp+arg_0], rbx
0x140018ec1  mov     [rsp+arg_18], rsi
0x140018ec6  push    rdi
0x140018ec7  sub     rsp, 0B70h
0x140018ece  mov     rsi, rcx
0x140018ed1  xor     edx, edx; Val
0x140018ed3  lea     rcx, [rsp+0B78h+var_B58]; void *
0x140018ed8  mov     r8d, 0B48h; Size
0x140018ede  call    memset_0
0x140018ee3  xor     edi, edi
0x140018ee5  mov     ecx, 807Eh
0x140018eea  mov     [rsp+0B78h+arg_10], rdi
0x140018ef2  call    IssueProgressStringResult
0x140018ef7  mov     ebx, eax
0x140018ef9  test    eax, eax
0x140018efb  jz      short loc_140018F6A
0x140018efd  cmp     qword ptr [rsi], 240h
0x140018f04  jz      short loc_140018F13
0x140018f06  xor     ebx, ebx
0x140018f08  lea     ecx, [rdi+18h]; dwErrCode
0x140018f0b  call    cs:__imp_SetLastError
0x140018f11  jmp     short loc_140018F6A
0x140018f13  movups  xmm0, xmmword ptr [rsi+10h]
0x140018f17  lea     rdx, [rsi+2Ch]; struct _GUID *
0x140018f1b  lea     r9, [rsp+0B78h+arg_10]; struct _SU_SPACE_OBJECT **
0x140018f23  lea     rcx, [rsp+0B78h+var_B58]; struct _SU_POOL_OBJECT *
0x140018f28  movdqu  [rsp+0B78h+var_B30], xmm0
0x140018f2e  call    ?SuGetSpaceFiltered@@YAHPEAU_SU_POOL_OBJECT@@PEAU_GUID@@KPEAPEAU_SU_SPACE_OBJECT@@@Z; SuGetSpaceFiltered(_SU_POOL_OBJECT *,_GUID *,ulong,_SU_SPACE_OBJECT * *)
0x140018f33  mov     rdi, [rsp+0B78h+arg_10]
0x140018f3b  mov     ebx, eax
0x140018f3d  test    eax, eax
0x140018f3f  jz      short loc_140018F6A
0x140018f41  movzx   eax, word ptr [rsi+23Ch]
0x140018f48  lea     r8, [rsi+3Ch]; unsigned __int16 *
0x140018f4c  lea     rdx, [rsi+20h]; unsigned __int16 *
0x140018f50  mov     [rsp+0B78h+arg_8], ax
0x140018f58  lea     r9, [rsp+0B78h+arg_8]; unsigned __int16 *
0x140018f60  mov     rcx, rdi; struct _SU_SPACE_OBJECT *
0x140018f63  call    ?SuReformatSpace@@YAHPEAU_SU_SPACE_OBJECT@@PEBG1PEAG@Z; SuReformatSpace(_SU_SPACE_OBJECT *,ushort const *,ushort const *,ushort *)
0x140018f68  mov     ebx, eax
0x140018f6a  call    cs:__imp_GetLastError
0x140018f70  mov     esi, eax
0x140018f72  test    rdi, rdi
0x140018f75  jz      short loc_140018F96
0x140018f77  mov     rcx, rdi; hMem
0x140018f7a  call    cs:__imp_LocalFree
0x140018f80  xor     ecx, ecx
0x140018f82  test    rax, rax
0x140018f85  setz    cl
0x140018f88  test    ebx, ebx
0x140018f8a  jz      short loc_140018F96
0x140018f8c  mov     ebx, ecx
0x140018f8e  call    cs:__imp_GetLastError
0x140018f94  mov     esi, eax
0x140018f96  mov     ecx, esi; dwErrCode
0x140018f98  call    cs:__imp_SetLastError
0x140018f9e  lea     r11, [rsp+0B78h+var_8]
0x140018fa6  mov     eax, ebx
0x140018fa8  mov     rbx, [r11+10h]
0x140018fac  mov     rsi, [r11+28h]
0x140018fb0  mov     rsp, r11
0x140018fb3  pop     rdi
0x140018fb4  retn
```
