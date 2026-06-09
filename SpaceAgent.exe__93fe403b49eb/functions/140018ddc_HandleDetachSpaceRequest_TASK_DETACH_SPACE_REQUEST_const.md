# HandleDetachSpaceRequest(TASK_DETACH_SPACE_REQUEST const *)

- ea: `0x140018ddc`
- end: `0x140018eb3`
- name: `?HandleDetachSpaceRequest@@YAHPEBUTASK_DETACH_SPACE_REQUEST@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(const struct TASK_DETACH_SPACE_REQUEST *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140017d70`

## callees

- `0x140001caf`
- `0x140012e28`
- `0x140016d64`
- `0x14001832c`
- `0x140018ddc`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140018e78`
- `KERNEL32!LocalFree` at `0x140018e78`
- `KERNEL32!SetLastError` at `0x140018e28`
- `KERNEL32!SetLastError` at `0x140018e96`
- `KERNEL32!SetLastError` at `0x140018e28`
- `KERNEL32!SetLastError` at `0x140018e96`
- `KERNEL32!GetLastError` at `0x140018e68`
- `KERNEL32!GetLastError` at `0x140018e8c`
- `KERNEL32!GetLastError` at `0x140018e68`
- `KERNEL32!GetLastError` at `0x140018e8c`

## pseudocode

```c
__int64 __fastcall HandleDetachSpaceRequest(const struct TASK_DETACH_SPACE_REQUEST *a1)
{
  struct _SU_SPACE_OBJECT *v2; // rdi
  unsigned int v3; // ebx
  unsigned int v4; // r8d
  int SpaceFiltered; // eax
  int v6; // edx
  DWORD LastError; // esi
  HLOCAL v8; // rax
  _BYTE v10[40]; // [rsp+20h] [rbp-B58h] BYREF
  __int128 v11; // [rsp+48h] [rbp-B30h]
  struct _SU_SPACE_OBJECT *v12; // [rsp+B88h] [rbp+10h] BYREF

  memset_0(v10, 0, 0xB48u);
  v2 = 0;
  v12 = 0;
  v3 = IssueProgressStringResult(32896);
  if ( v3 )
  {
    if ( *(_QWORD *)a1 == 48 )
    {
      v11 = *((_OWORD *)a1 + 1);
      SpaceFiltered = SuGetSpaceFiltered((struct _SU_POOL_OBJECT *)v10, (struct _GUID *)a1 + 2, v4, &v12);
      v2 = v12;
      v3 = SpaceFiltered;
      if ( SpaceFiltered )
        v3 = SuDetachSpaceEx(v12, v6);
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
    v8 = LocalFree(v2);
    if ( v3 )
    {
      v3 = v8 == 0;
      LastError = GetLastError();
    }
  }
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x140018ddc  mov     [rsp+arg_0], rbx
0x140018de1  mov     [rsp+arg_10], rsi
0x140018de6  push    rdi
0x140018de7  sub     rsp, 0B70h
0x140018dee  mov     rsi, rcx
0x140018df1  xor     edx, edx; Val
0x140018df3  lea     rcx, [rsp+0B78h+var_B58]; void *
0x140018df8  mov     r8d, 0B48h; Size
0x140018dfe  call    memset_0
0x140018e03  xor     edi, edi
0x140018e05  mov     ecx, 8080h
0x140018e0a  mov     [rsp+0B78h+arg_8], rdi
0x140018e12  call    IssueProgressStringResult
0x140018e17  mov     ebx, eax
0x140018e19  test    eax, eax
0x140018e1b  jz      short loc_140018E68
0x140018e1d  cmp     qword ptr [rsi], 30h ; '0'
0x140018e21  jz      short loc_140018E30
0x140018e23  xor     ebx, ebx
0x140018e25  lea     ecx, [rdi+18h]; dwErrCode
0x140018e28  call    cs:__imp_SetLastError
0x140018e2e  jmp     short loc_140018E68
0x140018e30  movups  xmm0, xmmword ptr [rsi+10h]
0x140018e34  lea     rdx, [rsi+20h]; struct _GUID *
0x140018e38  lea     r9, [rsp+0B78h+arg_8]; struct _SU_SPACE_OBJECT **
0x140018e40  lea     rcx, [rsp+0B78h+var_B58]; struct _SU_POOL_OBJECT *
0x140018e45  movdqu  [rsp+0B78h+var_B30], xmm0
0x140018e4b  call    ?SuGetSpaceFiltered@@YAHPEAU_SU_POOL_OBJECT@@PEAU_GUID@@KPEAPEAU_SU_SPACE_OBJECT@@@Z; SuGetSpaceFiltered(_SU_POOL_OBJECT *,_GUID *,ulong,_SU_SPACE_OBJECT * *)
0x140018e50  mov     rdi, [rsp+0B78h+arg_8]
0x140018e58  mov     ebx, eax
0x140018e5a  test    eax, eax
0x140018e5c  jz      short loc_140018E68
0x140018e5e  mov     rcx, rdi; struct _SU_SPACE_OBJECT *
0x140018e61  call    ?SuDetachSpaceEx@@YAHPEAU_SU_SPACE_OBJECT@@H@Z; SuDetachSpaceEx(_SU_SPACE_OBJECT *,int)
0x140018e66  mov     ebx, eax
0x140018e68  call    cs:__imp_GetLastError
0x140018e6e  mov     esi, eax
0x140018e70  test    rdi, rdi
0x140018e73  jz      short loc_140018E94
0x140018e75  mov     rcx, rdi; hMem
0x140018e78  call    cs:__imp_LocalFree
0x140018e7e  xor     ecx, ecx
0x140018e80  test    rax, rax
0x140018e83  setz    cl
0x140018e86  test    ebx, ebx
0x140018e88  jz      short loc_140018E94
0x140018e8a  mov     ebx, ecx
0x140018e8c  call    cs:__imp_GetLastError
0x140018e92  mov     esi, eax
0x140018e94  mov     ecx, esi; dwErrCode
0x140018e96  call    cs:__imp_SetLastError
0x140018e9c  lea     r11, [rsp+0B78h+var_8]
0x140018ea4  mov     eax, ebx
0x140018ea6  mov     rbx, [r11+10h]
0x140018eaa  mov     rsi, [r11+20h]
0x140018eae  mov     rsp, r11
0x140018eb1  pop     rdi
0x140018eb2  retn
```
