# RevertToOriginalSystemAccess(ulong)

- ea: `0x140004240`
- end: `0x14000436a`
- name: `?RevertToOriginalSystemAccess@@YAXK@Z`
- size: `298`
- prototype: `void __fastcall()`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400041b0`

## callees

- `0x140002738`
- `0x1400027cc`
- `0x140002818`
- `0x140004240`
- `0x140004c0c`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x14000427a`
- `ADVAPI32!OpenProcessToken` at `0x14000427a`
- `KERNEL32!CloseHandle` at `0x140004359`
- `KERNEL32!CloseHandle` at `0x140004359`
- `KERNEL32!GetCurrentProcess` at `0x140004264`
- `KERNEL32!GetCurrentProcess` at `0x140004264`
- `KERNEL32!GetLastError` at `0x140004284`
- `KERNEL32!GetLastError` at `0x140004284`

## string_xrefs

- `0x140004320`: `ModifySystemAccessInDacl failed!`

## pseudocode

```c
void __fastcall RevertToOriginalSystemAccess()
{
  DWORD v0; // edi
  HANDLE CurrentProcess; // rbx
  DWORD LastError; // ebx
  unsigned int v3; // eax
  int v4; // eax
  char v5; // bl
  int CurrentThreadActivityIdPrefix; // eax
  unsigned int v7; // [rsp+40h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  v0 = g_originalProcessAccessMaskForSystem;
  TokenHandle = 0;
  v7 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x60008u, &TokenHandle) )
  {
    v4 = CRdpSaUtils::s_ModifySystemAccessInDacl(CurrentProcess, TokenHandle, v0, &v7);
    v5 = v4;
    if ( v4 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"ModifySystemAccessInDacl failed!",
        v5);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids, v3, LastError);
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
}

```

## disassembly

```asm
0x140004240  mov     rax, rsp
0x140004243  mov     [rax+18h], rbx
0x140004247  mov     [rax+8], ecx
0x14000424a  push    rdi
0x14000424b  sub     rsp, 30h
0x14000424f  mov     edi, cs:?g_originalProcessAccessMaskForSystem@@3KA; ulong g_originalProcessAccessMaskForSystem
0x140004255  mov     qword ptr [rax+10h], 0
0x14000425d  mov     dword ptr [rax+8], 0
0x140004264  call    cs:__imp_GetCurrentProcess
0x14000426a  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x14000426f  mov     edx, 60008h; DesiredAccess
0x140004274  mov     rcx, rax; ProcessHandle
0x140004277  mov     rbx, rax
0x14000427a  call    cs:__imp_OpenProcessToken
0x140004280  test    eax, eax
0x140004282  jnz     short loc_1400042E1
0x140004284  call    cs:__imp_GetLastError
0x14000428a  mov     ebx, eax
0x14000428c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004293  lea     rdx, WPP_GLOBAL_Control
0x14000429a  cmp     rcx, rdx
0x14000429d  jz      loc_14000434F
0x1400042a3  test    byte ptr [rcx+1Ch], 8
0x1400042a7  jz      loc_14000434F
0x1400042ad  cmp     byte ptr [rcx+19h], 2
0x1400042b1  jb      loc_14000434F
0x1400042b7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400042bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400042c3  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x1400042ca  mov     edx, 0Ah
0x1400042cf  mov     dword ptr [rsp+38h+var_18], ebx
0x1400042d3  mov     r9d, eax
0x1400042d6  mov     rcx, [rcx+10h]
0x1400042da  call    WPP_SF_Dd
0x1400042df  jmp     short loc_14000434F
0x1400042e1  mov     rdx, [rsp+38h+TokenHandle]; void *
0x1400042e6  lea     r9, [rsp+38h+arg_0]; unsigned int *
0x1400042eb  mov     r8d, edi; unsigned int
0x1400042ee  mov     rcx, rbx; handle
0x1400042f1  call    ?s_ModifySystemAccessInDacl@CRdpSaUtils@@SAJPEAX0KPEAK@Z; CRdpSaUtils::s_ModifySystemAccessInDacl(void *,void *,ulong,ulong *)
0x1400042f6  mov     ebx, eax
0x1400042f8  test    eax, eax
0x1400042fa  jns     short loc_14000434F
0x1400042fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140004303  lea     rdx, WPP_GLOBAL_Control
0x14000430a  cmp     rcx, rdx
0x14000430d  jz      short loc_14000434F
0x14000430f  test    byte ptr [rcx+1Ch], 8
0x140004313  jz      short loc_14000434F
0x140004315  cmp     byte ptr [rcx+19h], 2
0x140004319  jb      short loc_14000434F
0x14000431b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004320  lea     rcx, aModifysystemac; "ModifySystemAccessInDacl failed!"
0x140004327  mov     [rsp+38h+var_10], ebx
0x14000432b  mov     [rsp+38h+var_18], rcx
0x140004330  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140004337  mov     rcx, cs:WPP_GLOBAL_Control
0x14000433e  mov     edx, 0Bh
0x140004343  mov     r9d, eax
0x140004346  mov     rcx, [rcx+10h]
0x14000434a  call    WPP_SF_DsD
0x14000434f  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x140004354  test    rcx, rcx
0x140004357  jz      short loc_14000435F
0x140004359  call    cs:__imp_CloseHandle
0x14000435f  mov     rbx, [rsp+38h+arg_10]
0x140004364  add     rsp, 30h
0x140004368  pop     rdi
0x140004369  retn
```
