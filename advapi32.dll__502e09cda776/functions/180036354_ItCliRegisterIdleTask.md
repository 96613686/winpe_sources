# ItCliRegisterIdleTask

- ea: `0x180036354`
- end: `0x1800364d1`
- name: `ItCliRegisterIdleTask`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x18003e3c0`

## callees

- `0x180036354`
- `0x1800720b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180036399`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180036399`
- `KERNEL32!GetLastError` at `0x1800363da`
- `KERNEL32!GetLastError` at `0x1800363da`
- `KERNEL32!CreateEventW` at `0x1800363c3`
- `KERNEL32!CreateEventW` at `0x180036401`
- `KERNEL32!CreateEventW` at `0x1800363c3`
- `KERNEL32!CreateEventW` at `0x180036401`
- `KERNEL32!CloseHandle` at `0x180036482`
- `KERNEL32!CloseHandle` at `0x18003649d`
- `KERNEL32!CloseHandle` at `0x180036482`
- `KERNEL32!CloseHandle` at `0x18003649d`
- `RPCRT4!NdrClientCall3` at `0x180036444`
- `RPCRT4!NdrClientCall3` at `0x180036444`

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
  LastError = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180075660, 0, 0, 0, a2, &v15, 1, 0, a3, a4).Pointer;
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
0x180036354  push    rbx
0x180036356  push    rsi
0x180036357  push    rdi
0x180036358  push    r12
0x18003635a  push    r14
0x18003635c  push    r15
0x18003635e  sub     rsp, 88h
0x180036365  mov     rax, cs:__security_cookie
0x18003636c  xor     rax, rsp
0x18003636f  mov     [rsp+0B8h+var_48], rax
0x180036374  mov     rsi, r9
0x180036377  mov     r15, r8
0x18003637a  mov     r12, rdx
0x18003637d  mov     ebx, ecx
0x18003637f  mov     [rsp+0B8h+var_78], r8
0x180036384  mov     [rsp+0B8h+var_70], r9
0x180036389  xorps   xmm0, xmm0
0x18003638c  movups  [rsp+0B8h+var_68], xmm0
0x180036391  movups  [rsp+0B8h+var_58], xmm0
0x180036396  xor     r14b, r14b
0x180036399  call    cs:__imp_GetCurrentProcessId
0x1800363a0  nop     dword ptr [rax+rax+00h]
0x1800363a5  mov     dword ptr [rsp+0B8h+var_68], 20h ; ' '
0x1800363ad  mov     dword ptr [rsp+0B8h+var_68+4], ebx
0x1800363b1  mov     dword ptr [rsp+0B8h+var_68+8], eax
0x1800363b5  xor     r9d, r9d; lpName
0x1800363b8  xor     r8d, r8d; bInitialState
0x1800363bb  lea     edi, [r9+1]
0x1800363bf  mov     edx, edi; bManualReset
0x1800363c1  xor     ecx, ecx; lpEventAttributes
0x1800363c3  call    cs:__imp_CreateEventW
0x1800363ca  nop     dword ptr [rax+rax+00h]
0x1800363cf  mov     [r15], rax
0x1800363d2  test    rax, rax
0x1800363d5  jnz     short loc_1800363ED
0x1800363d7  xor     dil, dil
0x1800363da  call    cs:__imp_GetLastError
0x1800363e1  nop     dword ptr [rax+rax+00h]
0x1800363e6  mov     ebx, eax
0x1800363e8  jmp     loc_180036476
0x1800363ed  mov     qword ptr [rsp+0B8h+var_58], rax
0x1800363f2  mov     [rsp+0B8h+var_88], dil
0x1800363f7  xor     r9d, r9d; lpName
0x1800363fa  mov     r8d, edi; bInitialState
0x1800363fd  mov     edx, edi; bManualReset
0x1800363ff  xor     ecx, ecx; lpEventAttributes
0x180036401  call    cs:__imp_CreateEventW
0x180036408  nop     dword ptr [rax+rax+00h]
0x18003640d  mov     [rsi], rax
0x180036410  test    rax, rax
0x180036413  jz      short loc_1800363DA
0x180036415  mov     qword ptr [rsp+0B8h+var_58+8], rax
0x18003641a  mov     r14b, dil
0x18003641d  mov     [rsp+0B8h+var_80], 0
0x180036426  lea     rax, [rsp+0B8h+var_68]
0x18003642b  mov     [rsp+0B8h+var_90], rax
0x180036430  mov     [rsp+0B8h+var_98], r12
0x180036435  xor     r9d, r9d
0x180036438  xor     r8d, r8d; pReturnValue
0x18003643b  xor     edx, edx; nProcNum
0x18003643d  lea     rcx, stru_180075660; pProxyInfo
0x180036444  call    cs:__imp_NdrClientCall3
0x18003644b  nop     dword ptr [rax+rax+00h]
0x180036450  mov     rbx, rax
0x180036453  mov     [rsp+0B8h+var_80], rax
0x180036458  mov     [rsp+0B8h+var_84], eax
0x18003645c  jmp     short loc_180036476
0x18003645e  mov     ebx, eax
0x180036460  mov     [rsp+0B8h+var_84], eax
0x180036464  mov     dil, [rsp+0B8h+var_88]
0x180036469  mov     r14b, dil
0x18003646c  mov     r15, [rsp+0B8h+var_78]
0x180036471  mov     rsi, [rsp+0B8h+var_70]
0x180036476  test    ebx, ebx
0x180036478  jz      short loc_1800364B0
0x18003647a  test    dil, dil
0x18003647d  jz      short loc_180036495
0x18003647f  mov     rcx, [r15]; hObject
0x180036482  call    cs:__imp_CloseHandle
0x180036489  nop     dword ptr [rax+rax+00h]
0x18003648e  mov     qword ptr [r15], 0
0x180036495  test    r14b, r14b
0x180036498  jz      short loc_1800364B0
0x18003649a  mov     rcx, [rsi]; hObject
0x18003649d  call    cs:__imp_CloseHandle
0x1800364a4  nop     dword ptr [rax+rax+00h]
0x1800364a9  mov     qword ptr [rsi], 0
0x1800364b0  mov     eax, ebx
0x1800364b2  mov     rcx, [rsp+0B8h+var_48]
0x1800364b7  xor     rcx, rsp; StackCookie
0x1800364ba  call    __security_check_cookie
0x1800364bf  add     rsp, 88h
0x1800364c6  pop     r15
0x1800364c8  pop     r14
0x1800364ca  pop     r12
0x1800364cc  pop     rdi
0x1800364cd  pop     rsi
0x1800364ce  pop     rbx
0x1800364cf  retn
0x18007278f  push    rbp
0x180072791  sub     rsp, 30h
0x180072795  mov     rbp, rdx
0x180072798  mov     rax, [rcx]
0x18007279b  cmp     dword ptr [rax], 0C0000005h
0x1800727a1  jz      short loc_1800727DA
0x1800727a3  cmp     dword ptr [rax], 0C0000194h
0x1800727a9  jz      short loc_1800727DA
0x1800727ab  cmp     dword ptr [rax], 0C00000AAh
0x1800727b1  jz      short loc_1800727DA
0x1800727b3  cmp     dword ptr [rax], 80000002h
0x1800727b9  jz      short loc_1800727DA
0x1800727bb  cmp     dword ptr [rax], 0C0000096h
0x1800727c1  jz      short loc_1800727DA
0x1800727c3  cmp     dword ptr [rax], 0C000001Dh
0x1800727c9  jz      short loc_1800727DA
0x1800727cb  cmp     dword ptr [rax], 80000003h
0x1800727d1  jz      short loc_1800727DA
0x1800727d3  mov     eax, 1
0x1800727d8  jmp     short loc_1800727DC
0x1800727da  xor     eax, eax
0x1800727dc  add     rsp, 30h
0x1800727e0  pop     rbp
0x1800727e1  retn
```
