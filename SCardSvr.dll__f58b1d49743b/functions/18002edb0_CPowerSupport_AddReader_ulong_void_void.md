# CPowerSupport::AddReader(ulong *,void * *,void * *)

- ea: `0x18002edb0`
- end: `0x18002ef43`
- name: `?AddReader@CPowerSupport@@SAKPEAKPEAPEAX1@Z`
- size: `403`
- prototype: `__int64 __fastcall(unsigned int *, void **, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d0c0`

## callees

- `0x1800156d4`
- `0x18001974c`
- `0x18002965c`
- `0x18002eb58`
- `0x18002ec1c`
- `0x18002edb0`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ee48`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ee48`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ee63`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ee88`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ee63`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ee88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eef4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ef02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eef4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ef02`

## string_xrefs

- `0x18002edee`: `CPowerSupport::AddReader`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPowerSupport::AddReader(unsigned int *a1, void **a2, void **a3)
{
  RTL_SRWLOCK *v5; // rbx
  struct CPowerSupport *v6; // rax
  HANDLE EventW; // rsi
  HANDLE v8; // rdi
  unsigned int i; // ebx
  struct CPowerSupport *v10; // rax
  struct CPowerSupport *v11; // rax
  struct CPowerSupport *v12; // rax
  DWORD v13; // ebx
  DWORD LastError; // [rsp+20h] [rbp-39h] BYREF
  int v16; // [rsp+24h] [rbp-35h] BYREF
  unsigned int *v17; // [rsp+28h] [rbp-31h] BYREF
  RTL_SRWLOCK *v18; // [rsp+30h] [rbp-29h] BYREF
  _QWORD *v19; // [rsp+38h] [rbp-21h] BYREF
  _QWORD v20[4]; // [rsp+40h] [rbp-19h] BYREF
  char v21[32]; // [rsp+60h] [rbp+7h] BYREF

  v17 = a1;
  LastError = 0;
  v16 = 0;
  strcpy(v21, "CPowerSupport::AddReader");
  v20[0] = v21;
  v20[1] = &v16;
  v20[2] = &LastError;
  v20[3] = &v17;
  lambda_8033b95b7c027b58bbc9660da4494b2c_::operator()(v20);
  v16 = 1;
  v19 = v20;
  v5 = (RTL_SRWLOCK *)((char *)CPowerSupport::Instance() + 16);
  AcquireSRWLockExclusive(v5);
  v18 = v5;
  v6 = CPowerSupport::Instance();
  EventW = CreateEventW(0, 0, *((unsigned __int8 *)v6 + 72), 0);
  if ( !EventW )
  {
    v8 = 0;
LABEL_3:
    LastError = GetLastError();
    goto LABEL_10;
  }
  v8 = CreateEventW(0, 0, 0, 0);
  if ( !v8 )
    goto LABEL_3;
  for ( i = 0; ; ++i )
  {
    v10 = CPowerSupport::Instance();
    if ( *((_DWORD *)v10 + 9) <= i || !*(_QWORD *)(*((_QWORD *)v10 + 5) + 8LL * (int)i) )
      break;
  }
  *a2 = EventW;
  v11 = CPowerSupport::Instance();
  CDynamicArray<void *>::Set((char *)v11 + 24, i, a2);
  *a3 = v8;
  v12 = CPowerSupport::Instance();
  CDynamicArray<void *>::Set((char *)v12 + 48, i, a3);
  *v17 = i;
LABEL_10:
  if ( LastError )
  {
    if ( EventW )
      CloseHandle(EventW);
    if ( v8 )
      CloseHandle(v8);
  }
  v13 = LastError;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v18);
  WppTraceUnwinder__lambda_8033b95b7c027b58bbc9660da4494b2c____::_WppTraceUnwinder__lambda_8033b95b7c027b58bbc9660da4494b2c____(&v19);
  return v13;
}

```

## disassembly

```asm
0x18002edb0  mov     [rsp-8+arg_18], rbx
0x18002edb5  push    rbp
0x18002edb6  push    rsi
0x18002edb7  push    rdi
0x18002edb8  push    r14
0x18002edba  push    r15
0x18002edbc  lea     rbp, [rsp-37h]
0x18002edc1  sub     rsp, 90h
0x18002edc8  mov     rax, cs:__security_cookie
0x18002edcf  xor     rax, rsp
0x18002edd2  mov     [rbp+57h+var_30], rax
0x18002edd6  mov     r15, r8
0x18002edd9  mov     r14, rdx
0x18002eddc  mov     [rbp+57h+var_88], rcx
0x18002ede0  mov     [rbp+57h+var_90], 0
0x18002ede7  mov     [rbp+57h+var_8C], 0
0x18002edee  movups  xmm0, xmmword ptr cs:aCpowersupportA; "CPowerSupport::AddReader"
0x18002edf5  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18002edf9  movups  xmm1, xmmword ptr cs:aCpowersupportA+9; "port::AddReader"
0x18002ee00  movups  xmmword ptr [rbp+57h+var_50+9], xmm1
0x18002ee04  lea     rax, [rbp+57h+var_50]
0x18002ee08  mov     [rbp+57h+var_70], rax
0x18002ee0c  lea     rax, [rbp+57h+var_8C]
0x18002ee10  mov     [rbp+57h+var_68], rax
0x18002ee14  lea     rax, [rbp+57h+var_90]
0x18002ee18  mov     [rbp+57h+var_60], rax
0x18002ee1c  lea     rax, [rbp+57h+var_88]
0x18002ee20  mov     [rbp+57h+var_58], rax
0x18002ee24  lea     rcx, [rbp+57h+var_70]
0x18002ee28  call    _lambda_8033b95b7c027b58bbc9660da4494b2c___operator__
0x18002ee2d  mov     [rbp+57h+var_8C], 1
0x18002ee34  lea     rax, [rbp+57h+var_70]
0x18002ee38  mov     [rbp+57h+var_78], rax
0x18002ee3c  call    ?Instance@CPowerSupport@@SAAEAV1@XZ; CPowerSupport::Instance(void)
0x18002ee41  lea     rbx, [rax+10h]
0x18002ee45  mov     rcx, rbx; SRWLock
0x18002ee48  call    cs:__imp_AcquireSRWLockExclusive
0x18002ee4e  mov     [rbp+57h+var_80], rbx
0x18002ee52  call    ?Instance@CPowerSupport@@SAAEAV1@XZ; CPowerSupport::Instance(void)
0x18002ee57  movzx   r8d, byte ptr [rax+48h]; bInitialState
0x18002ee5c  xor     r9d, r9d; lpName
0x18002ee5f  xor     edx, edx; bManualReset
0x18002ee61  xor     ecx, ecx; lpEventAttributes
0x18002ee63  call    cs:__imp_CreateEventW
0x18002ee69  mov     rsi, rax
0x18002ee6c  test    rax, rax
0x18002ee6f  jnz     short loc_18002EE7E
0x18002ee71  xor     edi, edi
0x18002ee73  call    cs:__imp_GetLastError
0x18002ee79  mov     [rbp+57h+var_90], eax
0x18002ee7c  jmp     short loc_18002EEE6
0x18002ee7e  xor     r9d, r9d; lpName
0x18002ee81  xor     r8d, r8d; bInitialState
0x18002ee84  xor     edx, edx; bManualReset
0x18002ee86  xor     ecx, ecx; lpEventAttributes
0x18002ee88  call    cs:__imp_CreateEventW
0x18002ee8e  mov     rdi, rax
0x18002ee91  test    rax, rax
0x18002ee94  jz      short loc_18002EE73
0x18002ee96  xor     ebx, ebx
0x18002ee98  call    ?Instance@CPowerSupport@@SAAEAV1@XZ; CPowerSupport::Instance(void)
0x18002ee9d  cmp     [rax+24h], ebx
0x18002eea0  jbe     short loc_18002EEB4
0x18002eea2  movsxd  rcx, ebx
0x18002eea5  mov     rax, [rax+28h]
0x18002eea9  cmp     qword ptr [rax+rcx*8], 0
0x18002eeae  jz      short loc_18002EEB4
0x18002eeb0  inc     ebx
0x18002eeb2  jmp     short loc_18002EE98
0x18002eeb4  mov     [r14], rsi
0x18002eeb7  call    ?Instance@CPowerSupport@@SAAEAV1@XZ; CPowerSupport::Instance(void)
0x18002eebc  lea     rcx, [rax+18h]
0x18002eec0  mov     r8, r14
0x18002eec3  mov     edx, ebx
0x18002eec5  call    ?Set@?$CDynamicArray@PEAX@@QEAAPEAPEAXHPEAPEAX@Z; CDynamicArray<void *>::Set(int,void * *)
0x18002eeca  mov     [r15], rdi
0x18002eecd  call    ?Instance@CPowerSupport@@SAAEAV1@XZ; CPowerSupport::Instance(void)
0x18002eed2  lea     rcx, [rax+30h]
0x18002eed6  mov     r8, r15
0x18002eed9  mov     edx, ebx
0x18002eedb  call    ?Set@?$CDynamicArray@PEAX@@QEAAPEAPEAXHPEAPEAX@Z; CDynamicArray<void *>::Set(int,void * *)
0x18002eee0  mov     rax, [rbp+57h+var_88]
0x18002eee4  mov     [rax], ebx
0x18002eee6  cmp     [rbp+57h+var_90], 0
0x18002eeea  jz      short loc_18002EF08
0x18002eeec  test    rsi, rsi
0x18002eeef  jz      short loc_18002EEFA
0x18002eef1  mov     rcx, rsi; hObject
0x18002eef4  call    cs:__imp_CloseHandle
0x18002eefa  test    rdi, rdi
0x18002eefd  jz      short loc_18002EF08
0x18002eeff  mov     rcx, rdi; hObject
0x18002ef02  call    cs:__imp_CloseHandle
0x18002ef08  mov     ebx, [rbp+57h+var_90]
0x18002ef0b  lea     rcx, [rbp+57h+var_80]
0x18002ef0f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002ef14  nop
0x18002ef15  lea     rcx, [rbp+57h+var_78]
0x18002ef19  call    WppTraceUnwinder__lambda_8033b95b7c027b58bbc9660da4494b2c_______WppTraceUnwinder__lambda_8033b95b7c027b58bbc9660da4494b2c____
0x18002ef1e  mov     eax, ebx
0x18002ef20  mov     rcx, [rbp+57h+var_30]
0x18002ef24  xor     rcx, rsp; StackCookie
0x18002ef27  call    __security_check_cookie
0x18002ef2c  mov     rbx, [rsp+0B0h+arg_18]
0x18002ef34  add     rsp, 90h
0x18002ef3b  pop     r15
0x18002ef3d  pop     r14
0x18002ef3f  pop     rdi
0x18002ef40  pop     rsi
0x18002ef41  pop     rbp
0x18002ef42  retn
```
