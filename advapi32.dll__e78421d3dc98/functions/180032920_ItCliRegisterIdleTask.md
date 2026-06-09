# ItCliRegisterIdleTask

- ea: `0x180032920`
- end: `0x180032a6f`
- name: `ItCliRegisterIdleTask`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x18003b2b0`

## callees

- `0x180032920`
- `0x180065090`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180032965`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180032965`
- `KERNEL32!GetLastError` at `0x18003299a`
- `KERNEL32!GetLastError` at `0x18003299a`
- `KERNEL32!CreateEventW` at `0x180032989`
- `KERNEL32!CreateEventW` at `0x1800329b8`
- `KERNEL32!CreateEventW` at `0x180032989`
- `KERNEL32!CreateEventW` at `0x1800329b8`
- `KERNEL32!CloseHandle` at `0x180032a2d`
- `KERNEL32!CloseHandle` at `0x180032a42`
- `KERNEL32!CloseHandle` at `0x180032a2d`
- `KERNEL32!CloseHandle` at `0x180032a42`
- `RPCRT4!NdrClientCall3` at `0x1800329f5`
- `RPCRT4!NdrClientCall3` at `0x1800329f5`

## pseudocode

```c
__int64 __fastcall ItCliRegisterIdleTask(int a1, __int64 a2, HANDLE *a3, HANDLE *a4)
{
  char v7; // r14
  char v8; // di
  HANDLE EventW; // rax
  DWORD LastError; // ebx
  HANDLE v11; // rax
  __int128 v15; // [rsp+50h] [rbp-68h] BYREF
  __int128 v16; // [rsp+60h] [rbp-58h]

  v15 = 0;
  v16 = 0;
  v7 = 0;
  LODWORD(v15) = 32;
  DWORD1(v15) = a1;
  DWORD2(v15) = GetCurrentProcessId();
  v8 = 1;
  EventW = CreateEventW(0, 1, 0, 0);
  *a3 = EventW;
  if ( !EventW )
  {
    v8 = 0;
LABEL_3:
    LastError = GetLastError();
    goto LABEL_6;
  }
  *(_QWORD *)&v16 = EventW;
  v11 = CreateEventW(0, 1, 1, 0);
  *a4 = v11;
  if ( !v11 )
    goto LABEL_3;
  *((_QWORD *)&v16 + 1) = v11;
  v7 = 1;
  LastError = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180067690, 0, 0, 0, a2, &v15, 1, 0, a3, a4).Pointer;
LABEL_6:
  if ( LastError )
  {
    if ( v8 )
    {
      CloseHandle(*a3);
      *a3 = 0;
    }
    if ( v7 )
    {
      CloseHandle(*a4);
      *a4 = 0;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180032920  push    rbx
0x180032922  push    rsi
0x180032923  push    rdi
0x180032924  push    r12
0x180032926  push    r14
0x180032928  push    r15
0x18003292a  sub     rsp, 88h
0x180032931  mov     rax, cs:__security_cookie
0x180032938  xor     rax, rsp
0x18003293b  mov     [rsp+0B8h+var_48], rax
0x180032940  mov     rsi, r9
0x180032943  mov     r15, r8
0x180032946  mov     r12, rdx
0x180032949  mov     ebx, ecx
0x18003294b  mov     [rsp+0B8h+var_78], r8
0x180032950  mov     [rsp+0B8h+var_70], r9
0x180032955  xorps   xmm0, xmm0
0x180032958  movups  [rsp+0B8h+var_68], xmm0
0x18003295d  movups  [rsp+0B8h+var_58], xmm0
0x180032962  xor     r14b, r14b
0x180032965  call    cs:__imp_GetCurrentProcessId
0x18003296b  mov     dword ptr [rsp+0B8h+var_68], 20h ; ' '
0x180032973  mov     dword ptr [rsp+0B8h+var_68+4], ebx
0x180032977  mov     dword ptr [rsp+0B8h+var_68+8], eax
0x18003297b  xor     r9d, r9d; lpName
0x18003297e  xor     r8d, r8d; bInitialState
0x180032981  lea     edi, [r9+1]
0x180032985  mov     edx, edi; bManualReset
0x180032987  xor     ecx, ecx; lpEventAttributes
0x180032989  call    cs:__imp_CreateEventW
0x18003298f  mov     [r15], rax
0x180032992  test    rax, rax
0x180032995  jnz     short loc_1800329A4
0x180032997  xor     dil, dil
0x18003299a  call    cs:__imp_GetLastError
0x1800329a0  mov     ebx, eax
0x1800329a2  jmp     short loc_180032A21
0x1800329a4  mov     qword ptr [rsp+0B8h+var_58], rax
0x1800329a9  mov     [rsp+0B8h+var_88], dil
0x1800329ae  xor     r9d, r9d; lpName
0x1800329b1  mov     r8d, edi; bInitialState
0x1800329b4  mov     edx, edi; bManualReset
0x1800329b6  xor     ecx, ecx; lpEventAttributes
0x1800329b8  call    cs:__imp_CreateEventW
0x1800329be  mov     [rsi], rax
0x1800329c1  test    rax, rax
0x1800329c4  jz      short loc_18003299A
0x1800329c6  mov     qword ptr [rsp+0B8h+var_58+8], rax
0x1800329cb  mov     r14b, dil
0x1800329ce  mov     [rsp+0B8h+var_80], 0
0x1800329d7  lea     rax, [rsp+0B8h+var_68]
0x1800329dc  mov     [rsp+0B8h+var_90], rax
0x1800329e1  mov     [rsp+0B8h+var_98], r12
0x1800329e6  xor     r9d, r9d
0x1800329e9  xor     r8d, r8d; pReturnValue
0x1800329ec  xor     edx, edx; nProcNum
0x1800329ee  lea     rcx, stru_180067690; pProxyInfo
0x1800329f5  call    cs:__imp_NdrClientCall3
0x1800329fb  mov     rbx, rax
0x1800329fe  mov     [rsp+0B8h+var_80], rax
0x180032a03  mov     [rsp+0B8h+var_84], eax
0x180032a07  jmp     short loc_180032A21
0x180032a09  mov     ebx, eax
0x180032a0b  mov     [rsp+0B8h+var_84], eax
0x180032a0f  mov     dil, [rsp+0B8h+var_88]
0x180032a14  mov     r14b, dil
0x180032a17  mov     r15, [rsp+0B8h+var_78]
0x180032a1c  mov     rsi, [rsp+0B8h+var_70]
0x180032a21  test    ebx, ebx
0x180032a23  jz      short loc_180032A4F
0x180032a25  test    dil, dil
0x180032a28  jz      short loc_180032A3A
0x180032a2a  mov     rcx, [r15]; hObject
0x180032a2d  call    cs:__imp_CloseHandle
0x180032a33  mov     qword ptr [r15], 0
0x180032a3a  test    r14b, r14b
0x180032a3d  jz      short loc_180032A4F
0x180032a3f  mov     rcx, [rsi]; hObject
0x180032a42  call    cs:__imp_CloseHandle
0x180032a48  mov     qword ptr [rsi], 0
0x180032a4f  mov     eax, ebx
0x180032a51  mov     rcx, [rsp+0B8h+var_48]
0x180032a56  xor     rcx, rsp; StackCookie
0x180032a59  call    __security_check_cookie
0x180032a5e  add     rsp, 88h
0x180032a65  pop     r15
0x180032a67  pop     r14
0x180032a69  pop     r12
0x180032a6b  pop     rdi
0x180032a6c  pop     rsi
0x180032a6d  pop     rbx
0x180032a6e  retn
0x1800656b2  push    rbp
0x1800656b4  sub     rsp, 30h
0x1800656b8  mov     rbp, rdx
0x1800656bb  mov     rax, [rcx]
0x1800656be  cmp     dword ptr [rax], 0C0000005h
0x1800656c4  jz      short loc_1800656FD
0x1800656c6  cmp     dword ptr [rax], 0C0000194h
0x1800656cc  jz      short loc_1800656FD
0x1800656ce  cmp     dword ptr [rax], 0C00000AAh
0x1800656d4  jz      short loc_1800656FD
0x1800656d6  cmp     dword ptr [rax], 80000002h
0x1800656dc  jz      short loc_1800656FD
0x1800656de  cmp     dword ptr [rax], 0C0000096h
0x1800656e4  jz      short loc_1800656FD
0x1800656e6  cmp     dword ptr [rax], 0C000001Dh
0x1800656ec  jz      short loc_1800656FD
0x1800656ee  cmp     dword ptr [rax], 80000003h
0x1800656f4  jz      short loc_1800656FD
0x1800656f6  mov     eax, 1
0x1800656fb  jmp     short loc_1800656FF
0x1800656fd  xor     eax, eax
0x1800656ff  add     rsp, 30h
0x180065703  pop     rbp
0x180065704  retn
```
