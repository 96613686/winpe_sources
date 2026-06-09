# HandleDestroySpaceRequest(TASK_DESTROY_SPACE_REQUEST const *)

- ea: `0x140018cfc`
- end: `0x140018dd3`
- name: `?HandleDestroySpaceRequest@@YAHPEBUTASK_DESTROY_SPACE_REQUEST@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(const struct TASK_DESTROY_SPACE_REQUEST *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140017d70`
- `0x140018a8c`

## callees

- `0x140001caf`
- `0x140012e28`
- `0x140016cb0`
- `0x14001832c`
- `0x140018cfc`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140018d98`
- `KERNEL32!LocalFree` at `0x140018d98`
- `KERNEL32!SetLastError` at `0x140018d48`
- `KERNEL32!SetLastError` at `0x140018db6`
- `KERNEL32!SetLastError` at `0x140018d48`
- `KERNEL32!SetLastError` at `0x140018db6`
- `KERNEL32!GetLastError` at `0x140018d88`
- `KERNEL32!GetLastError` at `0x140018dac`
- `KERNEL32!GetLastError` at `0x140018d88`
- `KERNEL32!GetLastError` at `0x140018dac`

## pseudocode

```c
__int64 __fastcall HandleDestroySpaceRequest(const struct TASK_DESTROY_SPACE_REQUEST *a1)
{
  struct _SU_SPACE_OBJECT *v2; // rdi
  unsigned int v3; // ebx
  unsigned int v4; // r8d
  int SpaceFiltered; // eax
  DWORD LastError; // esi
  HLOCAL v7; // rax
  _BYTE v9[40]; // [rsp+20h] [rbp-B58h] BYREF
  __int128 v10; // [rsp+48h] [rbp-B30h]
  struct _SU_SPACE_OBJECT *v11; // [rsp+B88h] [rbp+10h] BYREF

  memset_0(v9, 0, 0xB48u);
  v2 = 0;
  v11 = 0;
  v3 = IssueProgressStringResult(32892);
  if ( v3 )
  {
    if ( *(_QWORD *)a1 == 48 )
    {
      v10 = *((_OWORD *)a1 + 1);
      SpaceFiltered = SuGetSpaceFiltered((struct _SU_POOL_OBJECT *)v9, (struct _GUID *)a1 + 2, v4, &v11);
      v2 = v11;
      v3 = SpaceFiltered;
      if ( SpaceFiltered )
        v3 = SuDeleteSpaceEx(v11);
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
0x140018cfc  mov     [rsp+arg_0], rbx
0x140018d01  mov     [rsp+arg_10], rsi
0x140018d06  push    rdi
0x140018d07  sub     rsp, 0B70h
0x140018d0e  mov     rsi, rcx
0x140018d11  xor     edx, edx; Val
0x140018d13  lea     rcx, [rsp+0B78h+var_B58]; void *
0x140018d18  mov     r8d, 0B48h; Size
0x140018d1e  call    memset_0
0x140018d23  xor     edi, edi
0x140018d25  mov     ecx, 807Ch
0x140018d2a  mov     [rsp+0B78h+arg_8], rdi
0x140018d32  call    IssueProgressStringResult
0x140018d37  mov     ebx, eax
0x140018d39  test    eax, eax
0x140018d3b  jz      short loc_140018D88
0x140018d3d  cmp     qword ptr [rsi], 30h ; '0'
0x140018d41  jz      short loc_140018D50
0x140018d43  xor     ebx, ebx
0x140018d45  lea     ecx, [rdi+18h]; dwErrCode
0x140018d48  call    cs:__imp_SetLastError
0x140018d4e  jmp     short loc_140018D88
0x140018d50  movups  xmm0, xmmword ptr [rsi+10h]
0x140018d54  lea     rdx, [rsi+20h]; struct _GUID *
0x140018d58  lea     r9, [rsp+0B78h+arg_8]; struct _SU_SPACE_OBJECT **
0x140018d60  lea     rcx, [rsp+0B78h+var_B58]; struct _SU_POOL_OBJECT *
0x140018d65  movdqu  [rsp+0B78h+var_B30], xmm0
0x140018d6b  call    ?SuGetSpaceFiltered@@YAHPEAU_SU_POOL_OBJECT@@PEAU_GUID@@KPEAPEAU_SU_SPACE_OBJECT@@@Z; SuGetSpaceFiltered(_SU_POOL_OBJECT *,_GUID *,ulong,_SU_SPACE_OBJECT * *)
0x140018d70  mov     rdi, [rsp+0B78h+arg_8]
0x140018d78  mov     ebx, eax
0x140018d7a  test    eax, eax
0x140018d7c  jz      short loc_140018D88
0x140018d7e  mov     rcx, rdi; struct _SU_SPACE_OBJECT *
0x140018d81  call    ?SuDeleteSpaceEx@@YAHPEAU_SU_SPACE_OBJECT@@@Z; SuDeleteSpaceEx(_SU_SPACE_OBJECT *)
0x140018d86  mov     ebx, eax
0x140018d88  call    cs:__imp_GetLastError
0x140018d8e  mov     esi, eax
0x140018d90  test    rdi, rdi
0x140018d93  jz      short loc_140018DB4
0x140018d95  mov     rcx, rdi; hMem
0x140018d98  call    cs:__imp_LocalFree
0x140018d9e  xor     ecx, ecx
0x140018da0  test    rax, rax
0x140018da3  setz    cl
0x140018da6  test    ebx, ebx
0x140018da8  jz      short loc_140018DB4
0x140018daa  mov     ebx, ecx
0x140018dac  call    cs:__imp_GetLastError
0x140018db2  mov     esi, eax
0x140018db4  mov     ecx, esi; dwErrCode
0x140018db6  call    cs:__imp_SetLastError
0x140018dbc  lea     r11, [rsp+0B78h+var_8]
0x140018dc4  mov     eax, ebx
0x140018dc6  mov     rbx, [r11+10h]
0x140018dca  mov     rsi, [r11+20h]
0x140018dce  mov     rsp, r11
0x140018dd1  pop     rdi
0x140018dd2  retn
```
