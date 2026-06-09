# ThreadPool::WorkerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18001ed40`
- end: `0x18001ef73`
- name: `?WorkerCallback@ThreadPool@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `563`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001ed40`
- `0x18001ef7c`
- `0x180070eec`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ed86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ed86`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ee0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ef5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ee0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ef5f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001ee75`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001ef68`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001ee75`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001ef68`

## pseudocode

```c
void __fastcall ThreadPool::WorkerCallback(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WORK Work)
{
  _QWORD *v3; // rdi
  char *v5; // rbx
  char *v6; // rsi
  _QWORD *v7; // r14
  _QWORD *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  bool v11; // zf
  __int64 v12; // rsi
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  v3 = 0;
  v5 = Context;
  if ( Context )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)Context + 8LL))(Context);
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 136));
    v6 = (char *)*((_QWORD *)v5 + 14);
    if ( v6 == v5 + 112 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 136));
      CloseThreadpoolWork(Work);
LABEL_15:
      (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
      goto LABEL_16;
    }
    v7 = (_QWORD *)*((_QWORD *)v6 + 2);
    if ( v7 )
    {
      (*(void (__fastcall **)(_QWORD))(*v7 + 8LL))(*((_QWORD *)v6 + 2));
      v6 = (char *)*((_QWORD *)v5 + 14);
      v3 = v7;
    }
    v8 = (_QWORD *)*((_QWORD *)v6 + 1);
    v9 = *(_QWORD *)v6;
    *v8 = *(_QWORD *)v6;
    *(_QWORD *)(v9 + 8) = v8;
    v10 = *((_QWORD *)v6 + 2);
    if ( v10 )
    {
      *((_QWORD *)v6 + 2) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    operator delete(v6);
    --*((_QWORD *)v5 + 16);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 136));
    v11 = v3[2] == 0;
    v15 = 0;
    if ( v11 )
    {
      v12 = v3[3];
      if ( !v12 )
      {
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v15);
        goto LABEL_11;
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12 + 8LL))(v3[3]);
      v13 = v15;
      if ( !v15 )
      {
LABEL_11:
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 48LL))(v12, v3[4]);
        goto LABEL_12;
      }
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v15);
      v14 = v3[2];
      v12 = 0;
      v15 = 0;
      if ( !v14 )
        goto LABEL_11;
      if ( (*(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v14 + 24LL))(
             v14,
             &GUID_1f499b51_e97a_471c_af4a_945961d400a7,
             &v15) >= 0 )
      {
        v12 = v15;
        goto LABEL_11;
      }
      v13 = v15;
      if ( !v15 )
        goto LABEL_11;
    }
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    goto LABEL_11;
  }
  v12 = 0;
  v5 = 0;
LABEL_12:
  CloseThreadpoolWork(Work);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v5 )
    goto LABEL_15;
LABEL_16:
  if ( v3 )
    (*(void (__fastcall **)(_QWORD *))(*v3 + 16LL))(v3);
}

```

## disassembly

```asm
0x18001ed40  push    rdi
0x18001ed42  sub     rsp, 40h
0x18001ed46  mov     [rsp+48h+arg_0], rbx
0x18001ed4b  xor     edi, edi
0x18001ed4d  mov     [rsp+48h+arg_10], rbp
0x18001ed52  mov     rbp, r8
0x18001ed55  mov     [rsp+48h+var_10], rsi
0x18001ed5a  mov     rbx, rdx
0x18001ed5d  mov     [rsp+48h+var_18], r12
0x18001ed62  mov     [rsp+48h+var_28], r15
0x18001ed67  test    rdx, rdx
0x18001ed6a  jz      loc_18001EEEA
0x18001ed70  mov     rax, [rdx]
0x18001ed73  mov     rcx, rdx
0x18001ed76  mov     rax, [rax+8]
0x18001ed7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed7f  lea     rcx, [rbx+88h]; lpCriticalSection
0x18001ed86  call    cs:__imp_EnterCriticalSection
0x18001ed8c  mov     rsi, [rbx+70h]
0x18001ed90  lea     r15, [rbx+70h]
0x18001ed94  cmp     rsi, r15
0x18001ed97  jz      loc_18001EF58
0x18001ed9d  mov     [rsp+48h+var_20], r14
0x18001eda2  mov     r14, [rsi+10h]
0x18001eda6  test    r14, r14
0x18001eda9  jz      short loc_18001EDC0
0x18001edab  mov     rax, [r14]
0x18001edae  mov     rcx, r14
0x18001edb1  mov     rax, [rax+8]
0x18001edb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edba  mov     rsi, [r15]
0x18001edbd  mov     rdi, r14
0x18001edc0  mov     rcx, [rsi+8]
0x18001edc4  mov     rax, [rsi]
0x18001edc7  mov     r14, [rsp+48h+var_20]
0x18001edcc  mov     [rcx], rax
0x18001edcf  mov     [rax+8], rcx
0x18001edd3  mov     rcx, [rsi+10h]
0x18001edd7  test    rcx, rcx
0x18001edda  jz      short loc_18001EDF0
0x18001eddc  mov     qword ptr [rsi+10h], 0
0x18001ede4  mov     rax, [rcx]
0x18001ede7  mov     rax, [rax+10h]
0x18001edeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edf0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001edf7  mov     rcx, rsi; Block
0x18001edfa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001edff  dec     qword ptr [r15+10h]
0x18001ee03  lea     rcx, [rbx+88h]; lpCriticalSection
0x18001ee0a  call    cs:__imp_LeaveCriticalSection
0x18001ee10  cmp     qword ptr [rdi+10h], 0
0x18001ee15  mov     [rsp+48h+arg_8], 0
0x18001ee1e  jnz     loc_18001EEF0
0x18001ee24  mov     rsi, [rdi+18h]
0x18001ee28  test    rsi, rsi
0x18001ee2b  jz      loc_18001EEDB
0x18001ee31  mov     rax, [rsi]
0x18001ee34  mov     rcx, rsi
0x18001ee37  mov     rax, [rax+8]
0x18001ee3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee40  mov     rcx, [rsp+48h+arg_8]
0x18001ee45  test    rcx, rcx
0x18001ee48  jz      short loc_18001EE5F
0x18001ee4a  mov     [rsp+48h+arg_8], 0
0x18001ee53  mov     rax, [rcx]
0x18001ee56  mov     rax, [rax+10h]
0x18001ee5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee5f  mov     rax, [rsi]
0x18001ee62  mov     rcx, rsi
0x18001ee65  mov     rdx, [rdi+20h]
0x18001ee69  mov     rax, [rax+30h]
0x18001ee6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee72  mov     rcx, rbp; pwk
0x18001ee75  call    cs:__imp_CloseThreadpoolWork
0x18001ee7b  test    rsi, rsi
0x18001ee7e  jz      short loc_18001EE8F
0x18001ee80  mov     rax, [rsi]
0x18001ee83  mov     rcx, rsi
0x18001ee86  mov     rax, [rax+10h]
0x18001ee8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee8f  test    rbx, rbx
0x18001ee92  jz      short loc_18001EEA3
0x18001ee94  mov     rax, [rbx]
0x18001ee97  mov     rcx, rbx
0x18001ee9a  mov     rax, [rax+10h]
0x18001ee9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eea3  mov     r15, [rsp+48h+var_28]
0x18001eea8  mov     r12, [rsp+48h+var_18]
0x18001eead  mov     rsi, [rsp+48h+var_10]
0x18001eeb2  mov     rbp, [rsp+48h+arg_10]
0x18001eeb7  mov     rbx, [rsp+48h+arg_0]
0x18001eebc  test    rdi, rdi
0x18001eebf  jz      short loc_18001EED5
0x18001eec1  mov     rax, [rdi]
0x18001eec4  mov     rcx, rdi
0x18001eec7  mov     rax, [rax+10h]
0x18001eecb  add     rsp, 40h
0x18001eecf  pop     rdi
0x18001eed0  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18001eed5  add     rsp, 40h
0x18001eed9  pop     rdi
0x18001eeda  retn
0x18001eedb  lea     rcx, [rsp+48h+arg_8]
0x18001eee0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001eee5  jmp     loc_18001EE5F
0x18001eeea  xor     esi, esi
0x18001eeec  xor     ebx, ebx
0x18001eeee  jmp     short loc_18001EE72
0x18001eef0  lea     rcx, [rsp+48h+arg_8]
0x18001eef5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001eefa  mov     rcx, [rdi+10h]
0x18001eefe  xor     esi, esi
0x18001ef00  mov     [rsp+48h+arg_8], rsi
0x18001ef05  test    rcx, rcx
0x18001ef08  jz      loc_18001EE5F
0x18001ef0e  mov     rax, [rcx]
0x18001ef11  lea     r8, [rsp+48h+arg_8]
0x18001ef16  lea     rdx, _GUID_1f499b51_e97a_471c_af4a_945961d400a7
0x18001ef1d  mov     rax, [rax+18h]
0x18001ef21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef26  test    eax, eax
0x18001ef28  js      short loc_18001EF34
0x18001ef2a  mov     rsi, [rsp+48h+arg_8]
0x18001ef2f  jmp     loc_18001EE5F
0x18001ef34  mov     rcx, [rsp+48h+arg_8]
0x18001ef39  test    rcx, rcx
0x18001ef3c  jz      loc_18001EE5F
0x18001ef42  mov     [rsp+48h+arg_8], rsi
0x18001ef47  mov     rax, [rcx]
0x18001ef4a  mov     rax, [rax+10h]
0x18001ef4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef53  jmp     loc_18001EE5F
0x18001ef58  lea     rcx, [rbx+88h]; lpCriticalSection
0x18001ef5f  call    cs:__imp_LeaveCriticalSection
0x18001ef65  mov     rcx, rbp; pwk
0x18001ef68  call    cs:__imp_CloseThreadpoolWork
0x18001ef6e  jmp     loc_18001EE94
```
