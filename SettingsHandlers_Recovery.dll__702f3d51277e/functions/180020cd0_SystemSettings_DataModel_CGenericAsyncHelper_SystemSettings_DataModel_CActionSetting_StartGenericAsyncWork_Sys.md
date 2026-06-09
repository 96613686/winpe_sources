# SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CActionSetting>::StartGenericAsyncWork(SystemSettings::DataModel::CSettingBase *)

- ea: `0x180020cd0`
- end: `0x180020ef4`
- name: `?StartGenericAsyncWork@?$CGenericAsyncHelper@VCActionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEAVCSettingBase@23@@Z`
- size: `548`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180002380`
- `0x18000282c`
- `0x180013e04`
- `0x18001d6bc`
- `0x180020cd0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020da5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020da5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020eda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020eda`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180020e0a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180020e0a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CActionSetting>::StartGenericAsyncWork(
        __int64 a1,
        __int64 a2)
{
  HANDLE v4; // rax
  __int64 *v5; // rax
  __int64 v6; // rdx
  __int64 *v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  void *v10; // rcx
  __int64 v11; // rsi
  HANDLE Thread; // rbp
  bool v13; // sf
  __int64 v14; // rcx
  __int64 v15; // rcx
  signed int v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  signed int LastError; // eax
  int v20; // edx
  unsigned int v21; // r8d

  LODWORD(v4) = _InterlockedExchange((volatile __int32 *)(a1 + 216), 2);
  if ( !(_DWORD)v4 )
  {
    v5 = (__int64 *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v5;
    if ( !v5 )
    {
LABEL_33:
      LODWORD(v4) = SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CActionSetting>::DoAsyncWorkInternal(
                      a1,
                      a2);
      return (int)v4;
    }
    *v5 = 0;
    v5[1] = 0;
    if ( v5[1] != a2 )
    {
      if ( a2 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
      v8 = v7[1];
      v7[1] = a2;
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    if ( *v7 != a1 )
    {
      if ( a1 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      v9 = *v7;
      *v7 = a1;
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    v7[2] = 0;
    v10 = *(void **)(a1 + 232);
    if ( v10 )
    {
      WaitForSingleObject(v10, 0xFFFFFFFF);
      v11 = a1 + 224;
      if ( *(_QWORD *)(a1 + 232) )
      {
        if ( !(**(unsigned __int8 (__fastcall ***)(__int64))v11)(a1 + 224) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v20, v21);
          JUMPOUT(0x180020EF3LL);
        }
        *(_QWORD *)(a1 + 232) = 0;
      }
    }
    else
    {
      v11 = a1 + 224;
    }
    LOBYTE(v6) = 1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 168LL))(a2, v6);
    Thread = CreateThread(
               0,
               0,
               SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CActionSetting>::s_GenericAsyncThread,
               v7,
               0,
               0);
    v4 = *(HANDLE *)(v11 + 8);
    if ( Thread == v4 )
    {
      Thread = *(HANDLE *)(v11 + 8);
    }
    else
    {
      if ( v4 )
      {
        LODWORD(v4) = (**(__int64 (__fastcall ***)(__int64))v11)(v11);
        if ( !(_BYTE)v4 )
        {
          v16 = GetLastError();
          if ( v16 > 0 )
            v16 = (unsigned __int16)v16 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
          __debugbreak();
        }
        *(_QWORD *)(v11 + 8) = 0;
      }
      *(_QWORD *)(v11 + 8) = Thread;
    }
    if ( !Thread )
    {
      LODWORD(v4) = GetLastError();
      v13 = (int)v4 < 0;
      if ( (int)v4 > 0 )
      {
        LODWORD(v4) = (unsigned __int16)v4 | 0x80070000;
        v13 = (int)v4 < 0;
      }
      if ( v13 )
      {
        v14 = v7[1];
        if ( v14 )
        {
          v7[1] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        v15 = *v7;
        if ( *v7 )
        {
          *v7 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
        operator delete(v7);
        goto LABEL_33;
      }
    }
  }
  return (int)v4;
}

```

## disassembly

```asm
0x180020cd0  push    rbx
0x180020cd2  push    rbp
0x180020cd3  push    rsi
0x180020cd4  push    rdi
0x180020cd5  push    r14
0x180020cd7  sub     rsp, 30h
0x180020cdb  mov     r14, rdx
0x180020cde  mov     rdi, rcx
0x180020ce1  mov     eax, 2
0x180020ce6  xchg    eax, [rcx+0D8h]
0x180020cec  test    eax, eax
0x180020cee  jnz     loc_180020EB5
0x180020cf4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020cfb  lea     ecx, [rax+18h]; unsigned __int64
0x180020cfe  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180020d03  mov     rbx, rax
0x180020d06  test    rax, rax
0x180020d09  jz      loc_180020EAA
0x180020d0f  mov     qword ptr [rax], 0
0x180020d16  mov     qword ptr [rax+8], 0
0x180020d1e  cmp     [rax+8], r14
0x180020d22  jz      short loc_180020D53
0x180020d24  test    r14, r14
0x180020d27  jz      short loc_180020D39
0x180020d29  mov     rax, [r14]
0x180020d2c  mov     rcx, r14
0x180020d2f  mov     rax, [rax+8]
0x180020d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d38  nop
0x180020d39  mov     rcx, [rbx+8]
0x180020d3d  mov     [rbx+8], r14
0x180020d41  test    rcx, rcx
0x180020d44  jz      short loc_180020D53
0x180020d46  mov     rax, [rcx]
0x180020d49  mov     rax, [rax+10h]
0x180020d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d52  nop
0x180020d53  cmp     [rbx], rdi
0x180020d56  jz      short loc_180020D85
0x180020d58  test    rdi, rdi
0x180020d5b  jz      short loc_180020D6D
0x180020d5d  mov     rax, [rdi]
0x180020d60  mov     rcx, rdi
0x180020d63  mov     rax, [rax+8]
0x180020d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d6c  nop
0x180020d6d  mov     rcx, [rbx]
0x180020d70  mov     [rbx], rdi
0x180020d73  test    rcx, rcx
0x180020d76  jz      short loc_180020D85
0x180020d78  mov     rax, [rcx]
0x180020d7b  mov     rax, [rax+10h]
0x180020d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d84  nop
0x180020d85  mov     qword ptr [rbx+10h], 0
0x180020d8d  mov     rcx, [rdi+0E8h]; hHandle
0x180020d94  test    rcx, rcx
0x180020d97  jnz     short loc_180020DA2
0x180020d99  lea     rsi, [rdi+0E0h]
0x180020da0  jmp     short loc_180020DD7
0x180020da2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180020da5  call    cs:__imp_WaitForSingleObject
0x180020dab  lea     rsi, [rdi+0E0h]
0x180020db2  cmp     qword ptr [rsi+8], 0
0x180020db7  jz      short loc_180020DD7
0x180020db9  mov     rax, [rsi]
0x180020dbc  mov     rcx, rsi
0x180020dbf  mov     rax, [rax]
0x180020dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020dc7  test    al, al
0x180020dc9  jz      loc_180020EDA
0x180020dcf  mov     qword ptr [rsi+8], 0
0x180020dd7  mov     rax, [r14]
0x180020dda  mov     dl, 1
0x180020ddc  mov     rcx, r14
0x180020ddf  mov     rax, [rax+0A8h]
0x180020de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020deb  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x180020df4  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x180020dfc  mov     r9, rbx; lpParameter
0x180020dff  lea     r8, ?s_GenericAsyncThread@?$CGenericAsyncHelper@VCActionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpStartAddress
0x180020e06  xor     edx, edx; dwStackSize
0x180020e08  xor     ecx, ecx; lpThreadAttributes
0x180020e0a  call    cs:__imp_CreateThread
0x180020e10  mov     rbp, rax
0x180020e13  mov     rax, [rsi+8]
0x180020e17  cmp     rbp, rax
0x180020e1a  jz      short loc_180020E45
0x180020e1c  test    rax, rax
0x180020e1f  jz      short loc_180020E3F
0x180020e21  mov     rcx, [rsi]
0x180020e24  mov     rax, [rcx]
0x180020e27  mov     rcx, rsi
0x180020e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e2f  test    al, al
0x180020e31  jz      loc_180020EC0
0x180020e37  mov     qword ptr [rsi+8], 0
0x180020e3f  mov     [rsi+8], rbp
0x180020e43  jmp     short loc_180020E48
0x180020e45  mov     rbp, rax
0x180020e48  test    rbp, rbp
0x180020e4b  jnz     short loc_180020EB5
0x180020e4d  call    cs:__imp_GetLastError
0x180020e53  test    eax, eax
0x180020e55  jle     short loc_180020E61
0x180020e57  movzx   eax, ax
0x180020e5a  or      eax, 80070000h
0x180020e5f  test    eax, eax
0x180020e61  jns     short loc_180020EB5
0x180020e63  mov     rcx, [rbx+8]
0x180020e67  test    rcx, rcx
0x180020e6a  jz      short loc_180020E81
0x180020e6c  mov     qword ptr [rbx+8], 0
0x180020e74  mov     rax, [rcx]
0x180020e77  mov     rax, [rax+10h]
0x180020e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e80  nop
0x180020e81  mov     rcx, [rbx]
0x180020e84  test    rcx, rcx
0x180020e87  jz      short loc_180020E9D
0x180020e89  mov     qword ptr [rbx], 0
0x180020e90  mov     rax, [rcx]
0x180020e93  mov     rax, [rax+10h]
0x180020e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e9c  nop
0x180020e9d  mov     edx, 18h
0x180020ea2  mov     rcx, rbx; Block
0x180020ea5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020eaa  mov     rdx, r14
0x180020ead  mov     rcx, rdi
0x180020eb0  call    ?DoAsyncWorkInternal@?$CGenericAsyncHelper@VCActionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CActionSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *)
0x180020eb5  add     rsp, 30h
0x180020eb9  pop     r14
0x180020ebb  pop     rdi
0x180020ebc  pop     rsi
0x180020ebd  pop     rbp
0x180020ebe  pop     rbx
0x180020ebf  retn
0x180020ec0  call    cs:__imp_GetLastError
0x180020ec6  test    eax, eax
0x180020ec8  jle     short loc_180020ED2
0x180020eca  movzx   eax, ax
0x180020ecd  or      eax, 80070000h
0x180020ed2  mov     ecx, eax; this
0x180020ed4  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180020ed9  int     3; Trap to Debugger
0x180020eda  call    cs:__imp_GetLastError
0x180020ee0  test    eax, eax
0x180020ee2  jle     short loc_180020EEC
0x180020ee4  movzx   eax, ax
0x180020ee7  or      eax, 80070000h
0x180020eec  mov     ecx, eax; this
0x180020eee  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
