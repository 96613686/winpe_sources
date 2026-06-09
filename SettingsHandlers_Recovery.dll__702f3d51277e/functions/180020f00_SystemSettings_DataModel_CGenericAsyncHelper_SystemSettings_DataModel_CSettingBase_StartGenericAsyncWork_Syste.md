# SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::StartGenericAsyncWork(SystemSettings::DataModel::CSettingBase *)

- ea: `0x180020f00`
- end: `0x180021124`
- name: `?StartGenericAsyncWork@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEAVCSettingBase@23@@Z`
- size: `548`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180002380`
- `0x18000282c`
- `0x180013eac`
- `0x18001d6bc`
- `0x180020f00`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020fd5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020fd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002107d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002110a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002107d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002110a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002103a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002103a`

## pseudocode

```c
int __fastcall SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::StartGenericAsyncWork(
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

  LODWORD(v4) = _InterlockedExchange((volatile __int32 *)(a1 + 160), 2);
  if ( !(_DWORD)v4 )
  {
    v5 = (__int64 *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v5;
    if ( !v5 )
    {
LABEL_33:
      LODWORD(v4) = SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::DoAsyncWorkInternal(
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
    v10 = *(void **)(a1 + 176);
    if ( v10 )
    {
      WaitForSingleObject(v10, 0xFFFFFFFF);
      v11 = a1 + 168;
      if ( *(_QWORD *)(a1 + 176) )
      {
        if ( !(**(unsigned __int8 (__fastcall ***)(__int64))v11)(a1 + 168) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v20, v21);
          JUMPOUT(0x180021123LL);
        }
        *(_QWORD *)(a1 + 176) = 0;
      }
    }
    else
    {
      v11 = a1 + 168;
    }
    LOBYTE(v6) = 1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 168LL))(a2, v6);
    Thread = CreateThread(
               0,
               0,
               SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::s_GenericAsyncThread,
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
0x180020f00  push    rbx
0x180020f02  push    rbp
0x180020f03  push    rsi
0x180020f04  push    rdi
0x180020f05  push    r14
0x180020f07  sub     rsp, 30h
0x180020f0b  mov     r14, rdx
0x180020f0e  mov     rdi, rcx
0x180020f11  mov     eax, 2
0x180020f16  xchg    eax, [rcx+0A0h]
0x180020f1c  test    eax, eax
0x180020f1e  jnz     loc_1800210E5
0x180020f24  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020f2b  lea     ecx, [rax+18h]; unsigned __int64
0x180020f2e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180020f33  mov     rbx, rax
0x180020f36  test    rax, rax
0x180020f39  jz      loc_1800210DA
0x180020f3f  mov     qword ptr [rax], 0
0x180020f46  mov     qword ptr [rax+8], 0
0x180020f4e  cmp     [rax+8], r14
0x180020f52  jz      short loc_180020F83
0x180020f54  test    r14, r14
0x180020f57  jz      short loc_180020F69
0x180020f59  mov     rax, [r14]
0x180020f5c  mov     rcx, r14
0x180020f5f  mov     rax, [rax+8]
0x180020f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f68  nop
0x180020f69  mov     rcx, [rbx+8]
0x180020f6d  mov     [rbx+8], r14
0x180020f71  test    rcx, rcx
0x180020f74  jz      short loc_180020F83
0x180020f76  mov     rax, [rcx]
0x180020f79  mov     rax, [rax+10h]
0x180020f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f82  nop
0x180020f83  cmp     [rbx], rdi
0x180020f86  jz      short loc_180020FB5
0x180020f88  test    rdi, rdi
0x180020f8b  jz      short loc_180020F9D
0x180020f8d  mov     rax, [rdi]
0x180020f90  mov     rcx, rdi
0x180020f93  mov     rax, [rax+8]
0x180020f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f9c  nop
0x180020f9d  mov     rcx, [rbx]
0x180020fa0  mov     [rbx], rdi
0x180020fa3  test    rcx, rcx
0x180020fa6  jz      short loc_180020FB5
0x180020fa8  mov     rax, [rcx]
0x180020fab  mov     rax, [rax+10h]
0x180020faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020fb4  nop
0x180020fb5  mov     qword ptr [rbx+10h], 0
0x180020fbd  mov     rcx, [rdi+0B0h]; hHandle
0x180020fc4  test    rcx, rcx
0x180020fc7  jnz     short loc_180020FD2
0x180020fc9  lea     rsi, [rdi+0A8h]
0x180020fd0  jmp     short loc_180021007
0x180020fd2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180020fd5  call    cs:__imp_WaitForSingleObject
0x180020fdb  lea     rsi, [rdi+0A8h]
0x180020fe2  cmp     qword ptr [rsi+8], 0
0x180020fe7  jz      short loc_180021007
0x180020fe9  mov     rax, [rsi]
0x180020fec  mov     rcx, rsi
0x180020fef  mov     rax, [rax]
0x180020ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ff7  test    al, al
0x180020ff9  jz      loc_18002110A
0x180020fff  mov     qword ptr [rsi+8], 0
0x180021007  mov     rax, [r14]
0x18002100a  mov     dl, 1
0x18002100c  mov     rcx, r14
0x18002100f  mov     rax, [rax+0A8h]
0x180021016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002101b  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x180021024  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18002102c  mov     r9, rbx; lpParameter
0x18002102f  lea     r8, ?s_GenericAsyncThread@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpStartAddress
0x180021036  xor     edx, edx; dwStackSize
0x180021038  xor     ecx, ecx; lpThreadAttributes
0x18002103a  call    cs:__imp_CreateThread
0x180021040  mov     rbp, rax
0x180021043  mov     rax, [rsi+8]
0x180021047  cmp     rbp, rax
0x18002104a  jz      short loc_180021075
0x18002104c  test    rax, rax
0x18002104f  jz      short loc_18002106F
0x180021051  mov     rcx, [rsi]
0x180021054  mov     rax, [rcx]
0x180021057  mov     rcx, rsi
0x18002105a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002105f  test    al, al
0x180021061  jz      loc_1800210F0
0x180021067  mov     qword ptr [rsi+8], 0
0x18002106f  mov     [rsi+8], rbp
0x180021073  jmp     short loc_180021078
0x180021075  mov     rbp, rax
0x180021078  test    rbp, rbp
0x18002107b  jnz     short loc_1800210E5
0x18002107d  call    cs:__imp_GetLastError
0x180021083  test    eax, eax
0x180021085  jle     short loc_180021091
0x180021087  movzx   eax, ax
0x18002108a  or      eax, 80070000h
0x18002108f  test    eax, eax
0x180021091  jns     short loc_1800210E5
0x180021093  mov     rcx, [rbx+8]
0x180021097  test    rcx, rcx
0x18002109a  jz      short loc_1800210B1
0x18002109c  mov     qword ptr [rbx+8], 0
0x1800210a4  mov     rax, [rcx]
0x1800210a7  mov     rax, [rax+10h]
0x1800210ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210b0  nop
0x1800210b1  mov     rcx, [rbx]
0x1800210b4  test    rcx, rcx
0x1800210b7  jz      short loc_1800210CD
0x1800210b9  mov     qword ptr [rbx], 0
0x1800210c0  mov     rax, [rcx]
0x1800210c3  mov     rax, [rax+10h]
0x1800210c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210cc  nop
0x1800210cd  mov     edx, 18h
0x1800210d2  mov     rcx, rbx; Block
0x1800210d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800210da  mov     rdx, r14
0x1800210dd  mov     rcx, rdi
0x1800210e0  call    ?DoAsyncWorkInternal@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *)
0x1800210e5  add     rsp, 30h
0x1800210e9  pop     r14
0x1800210eb  pop     rdi
0x1800210ec  pop     rsi
0x1800210ed  pop     rbp
0x1800210ee  pop     rbx
0x1800210ef  retn
0x1800210f0  call    cs:__imp_GetLastError
0x1800210f6  test    eax, eax
0x1800210f8  jle     short loc_180021102
0x1800210fa  movzx   eax, ax
0x1800210fd  or      eax, 80070000h
0x180021102  mov     ecx, eax; this
0x180021104  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180021109  int     3; Trap to Debugger
0x18002110a  call    cs:__imp_GetLastError
0x180021110  test    eax, eax
0x180021112  jle     short loc_18002111C
0x180021114  movzx   eax, ax
0x180021117  or      eax, 80070000h
0x18002111c  mov     ecx, eax; this
0x18002111e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
