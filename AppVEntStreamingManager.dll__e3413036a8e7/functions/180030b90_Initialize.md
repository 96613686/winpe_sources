# Initialize

- ea: `0x180030b90`
- end: `0x180030e5a`
- name: `Initialize`
- size: `714`
- prototype: `HRESULT __cdecl()`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180002b24`
- `0x18000d3e8`
- `0x18000d90c`
- `0x18000e5d4`
- `0x180021f70`
- `0x180030b90`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180030be9`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180030be9`
- `KERNEL32!GetCurrentThreadId` at `0x180030bc7`
- `KERNEL32!GetCurrentThreadId` at `0x180030bc7`
- `KERNEL32!InitializeCriticalSection` at `0x180030c92`
- `KERNEL32!InitializeCriticalSection` at `0x180030c92`
- `KERNEL32!LeaveCriticalSection` at `0x180030e44`
- `KERNEL32!LeaveCriticalSection` at `0x180030e44`
- `KERNEL32!EnterCriticalSection` at `0x180030ba7`
- `KERNEL32!EnterCriticalSection` at `0x180030ba7`

## pseudocode

```c
HRESULT __cdecl Initialize()
{
  __int64 v0; // rcx
  __int64 v1; // rbp
  char *v2; // rax
  const char *v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rbx
  __int128 v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  volatile signed __int32 *v12; // rbx
  __int128 v14; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v15[2]; // [rsp+30h] [rbp-58h] BYREF
  __int16 v16; // [rsp+43h] [rbp-45h]
  char v17; // [rsp+45h] [rbp-43h]

  v1 = v0;
  EnterCriticalSection(&CriticalSection);
  LODWORD(qword_1800AA688) = qword_1800AA688 + 1;
  if ( (_DWORD)qword_1800AA688 == 1 )
    HIDWORD(qword_1800AA688) = GetCurrentThreadId();
  if ( qword_1800AA8A0 )
  {
    v2 = strrchr("admin\\appman\\appv\\client\\streaming\\interface.cpp", 92);
    if ( v2 )
      v3 = v2 + 1;
    else
      v3 = "admin\\appman\\appv\\client\\streaming\\interface.cpp";
    v4 = (sub_180021F70(&qword_1800AA650, v3) << 52) | 0x70C00000002LL;
    LODWORD(qword_1800AA688) = qword_1800AA688 - 1;
    if ( !(_DWORD)qword_1800AA688 )
      qword_1800AA688 = 0;
  }
  else
  {
    v5 = sub_180002B24(152);
    *(_QWORD *)v5 = &AppV::Client::Streaming::CancelManagerImpl::`vftable';
    *(_QWORD *)(v5 + 16) = sub_180002B24(168);
    v15[0] = 0;
    v16 = 0;
    v17 = 0;
    sub_18000D90C(v5 + 32, v15);
    *(_QWORD *)(v5 + 96) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v5 + 104));
    *(_QWORD *)(v5 + 144) = 0;
    *((_QWORD *)&v8 + 1) = sub_180002B24(24);
    *(_DWORD *)(*((_QWORD *)&v8 + 1) + 8LL) = 1;
    *(_DWORD *)(*((_QWORD *)&v8 + 1) + 12LL) = 1;
    **((_QWORD **)&v8 + 1) = &std::_Ref_count<AppV::Client::Streaming::CancelManagerImpl>::`vftable';
    *(_QWORD *)(*((_QWORD *)&v8 + 1) + 16LL) = v5;
    v6 = sub_180002B24(280);
    v14 = 0;
    _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v8 + 1) + 8LL), 1u);
    v14 = v8;
    v7 = sub_18000D3E8(v6, v1, &v14);
    *(_QWORD *)&v8 = sub_180002B24(24);
    *(_DWORD *)(v8 + 8) = 1;
    *(_DWORD *)(v8 + 12) = 1;
    *(_QWORD *)v8 = &std::_Ref_count<AppV::Client::Streaming::EnterprisePolicyAdapter<Streaming::StreamingManager<strategy::enterprise::streaming_strategy>,AppV::Client::Streaming::DirectoryDaclManager_T<AppV::Client::Streaming::EmptyDirectoryDaclManagerBase>>>::`vftable';
    *(_QWORD *)(v8 + 16) = v7;
    v9 = sub_180002B24(168);
    _InterlockedAdd((volatile signed __int32 *)(v8 + 8), 1u);
    v15[0] = v7;
    v15[1] = v8;
    v10 = sub_18000E5D4(v9, v1, v15);
    v11 = sub_180002B24(24);
    *(_DWORD *)(v11 + 8) = 1;
    *(_DWORD *)(v11 + 12) = 1;
    *(_QWORD *)v11 = &std::_Ref_count<AppV::Client::Streaming::StreamingManager>::`vftable';
    *(_QWORD *)(v11 + 16) = v10;
    qword_1800AA8A0 = v10;
    v12 = (volatile signed __int32 *)qword_1800AA8A8;
    qword_1800AA8A8 = v11;
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v8 + 8), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(_QWORD))v8)(v8);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v8 + 12), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8 + 8LL))(v8);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v8 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (***((void (__fastcall ****)(_QWORD))&v8 + 1))(*((_QWORD *)&v8 + 1));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v8 + 1) + 12LL), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v8 + 1) + 8LL))(*((_QWORD *)&v8 + 1));
    }
    LODWORD(qword_1800AA688) = qword_1800AA688 - 1;
    if ( !(_DWORD)qword_1800AA688 )
      qword_1800AA688 = 0;
    LODWORD(v4) = 0;
  }
  LeaveCriticalSection(&CriticalSection);
  return v4;
}

```

## disassembly

```asm
0x180030b90  push    rbx
0x180030b92  push    rbp
0x180030b93  push    rsi
0x180030b94  push    rdi
0x180030b95  push    r12
0x180030b97  push    r14
0x180030b99  sub     rsp, 58h
0x180030b9d  mov     rbp, rcx
0x180030ba0  lea     rcx, CriticalSection; lpCriticalSection
0x180030ba7  call    cs:EnterCriticalSection
0x180030bad  mov     eax, dword ptr cs:qword_1800AA688
0x180030bb3  mov     r12d, 1
0x180030bb9  add     eax, r12d
0x180030bbc  mov     dword ptr cs:qword_1800AA688, eax
0x180030bc2  cmp     eax, r12d
0x180030bc5  jnz     short loc_180030BD3
0x180030bc7  call    cs:GetCurrentThreadId
0x180030bcd  mov     dword ptr cs:qword_1800AA688+4, eax
0x180030bd3  cmp     cs:qword_1800AA8A0, 0
0x180030bdb  jz      short loc_180030C3F
0x180030bdd  mov     edx, 5Ch ; '\'; Ch
0x180030be2  lea     rcx, aAdminAppmanApp_3; "admin\\appman\\appv\\client\\streaming"...
0x180030be9  call    cs:strrchr
0x180030bef  test    rax, rax
0x180030bf2  jz      short loc_180030BF9
0x180030bf4  add     rax, r12
0x180030bf7  jmp     short loc_180030C00
0x180030bf9  lea     rax, aAdminAppmanApp_3; "admin\\appman\\appv\\client\\streaming"...
0x180030c00  mov     rdx, rax
0x180030c03  lea     rcx, qword_1800AA650
0x180030c0a  call    sub_180021F70
0x180030c0f  mov     rbx, rax
0x180030c12  mov     rax, 70C00000002h
0x180030c1c  shl     rbx, 34h
0x180030c20  or      rbx, rax
0x180030c23  sub     dword ptr cs:qword_1800AA688, r12d
0x180030c2a  jnz     loc_180030E3D
0x180030c30  mov     dword ptr cs:qword_1800AA688+4, 0
0x180030c3a  jmp     loc_180030E3D
0x180030c3f  mov     ecx, 98h
0x180030c44  call    sub_180002B24
0x180030c49  mov     rdi, rax
0x180030c4c  mov     ecx, 0A8h
0x180030c51  lea     rax, ??_7CancelManagerImpl@Streaming@Client@AppV@@6B@; const AppV::Client::Streaming::CancelManagerImpl::`vftable'
0x180030c58  mov     [rdi], rax
0x180030c5b  call    sub_180002B24
0x180030c60  mov     [rdi+10h], rax
0x180030c64  lea     rcx, [rdi+20h]
0x180030c68  xor     eax, eax
0x180030c6a  mov     [rsp+88h+var_58], 0
0x180030c73  lea     rdx, [rsp+88h+var_58]
0x180030c78  mov     [rsp+88h+var_45], ax
0x180030c7d  mov     [rsp+88h+var_43], al
0x180030c81  call    sub_18000D90C
0x180030c86  lea     rcx, [rdi+68h]; lpCriticalSection
0x180030c8a  mov     qword ptr [rdi+60h], 0
0x180030c92  call    cs:InitializeCriticalSection
0x180030c98  mov     r14d, 18h
0x180030c9e  mov     qword ptr [rdi+90h], 0
0x180030ca9  mov     ecx, r14d
0x180030cac  call    sub_180002B24
0x180030cb1  mov     rsi, rax
0x180030cb4  mov     ecx, 118h
0x180030cb9  mov     [rax+8], r12d
0x180030cbd  mov     [rax+0Ch], r12d
0x180030cc1  lea     rax, ??_7?$_Ref_count@VCancelManagerImpl@Streaming@Client@AppV@@@std@@6B@; const std::_Ref_count<AppV::Client::Streaming::CancelManagerImpl>::`vftable'
0x180030cc8  mov     [rsi], rax
0x180030ccb  mov     [rsi+10h], rdi
0x180030ccf  call    sub_180002B24
0x180030cd4  xorps   xmm0, xmm0
0x180030cd7  movdqu  [rsp+88h+var_68], xmm0
0x180030cdd  lock add [rsi+8], r12d
0x180030ce2  lea     r8, [rsp+88h+var_68]
0x180030ce7  mov     qword ptr [rsp+88h+var_68], rdi
0x180030cec  mov     rdx, rbp
0x180030cef  mov     qword ptr [rsp+88h+var_68+8], rsi
0x180030cf4  mov     rcx, rax
0x180030cf7  call    sub_18000D3E8
0x180030cfc  mov     ecx, r14d
0x180030cff  mov     rbx, rax
0x180030d02  call    sub_180002B24
0x180030d07  mov     rdi, rax
0x180030d0a  mov     ecx, 0A8h
0x180030d0f  mov     [rax+8], r12d
0x180030d13  mov     [rax+0Ch], r12d
0x180030d17  lea     rax, ??_7?$_Ref_count@V?$EnterprisePolicyAdapter@V?$StreamingManager@Ustreaming_strategy@enterprise@strategy@@@Streaming@@V?$DirectoryDaclManager_T@UEmptyDirectoryDaclManagerBase@Streaming@Client@AppV@@@2Client@AppV@@@Streaming@Client@AppV@@@std@@6B@; const std::_Ref_count<AppV::Client::Streaming::EnterprisePolicyAdapter<Streaming::StreamingManager<strategy::enterprise::streaming_strategy>,AppV::Client::Streaming::DirectoryDaclManager_T<AppV::Client::Streaming::EmptyDirectoryDaclManagerBase>>>::`vftable'
0x180030d1e  mov     [rdi], rax
0x180030d21  mov     [rdi+10h], rbx
0x180030d25  call    sub_180002B24
0x180030d2a  lock add [rdi+8], r12d
0x180030d2f  lea     r8, [rsp+88h+var_58]
0x180030d34  mov     [rsp+88h+var_58], rbx
0x180030d39  mov     rdx, rbp
0x180030d3c  mov     [rsp+88h+var_50], rdi
0x180030d41  mov     rcx, rax
0x180030d44  call    sub_18000E5D4
0x180030d49  mov     ecx, r14d
0x180030d4c  mov     rbx, rax
0x180030d4f  call    sub_180002B24
0x180030d54  lea     rcx, ??_7?$_Ref_count@VStreamingManager@Streaming@Client@AppV@@@std@@6B@; const std::_Ref_count<AppV::Client::Streaming::StreamingManager>::`vftable'
0x180030d5b  or      ebp, 0FFFFFFFFh
0x180030d5e  mov     [rax+8], r12d
0x180030d62  mov     [rax+0Ch], r12d
0x180030d66  mov     [rax], rcx
0x180030d69  mov     [rax+10h], rbx
0x180030d6d  mov     cs:qword_1800AA8A0, rbx
0x180030d74  mov     rbx, cs:qword_1800AA8A8
0x180030d7b  mov     cs:qword_1800AA8A8, rax
0x180030d82  test    rbx, rbx
0x180030d85  jz      short loc_180030DBA
0x180030d87  mov     eax, ebp
0x180030d89  lock xadd [rbx+8], eax
0x180030d8e  add     eax, ebp
0x180030d90  jnz     short loc_180030DBA
0x180030d92  mov     rax, [rbx]
0x180030d95  mov     rcx, rbx
0x180030d98  mov     rax, [rax]
0x180030d9b  call    j__guard_dispatch_icall
0x180030da0  mov     eax, ebp
0x180030da2  lock xadd [rbx+0Ch], eax
0x180030da7  add     eax, ebp
0x180030da9  jnz     short loc_180030DBA
0x180030dab  mov     rax, [rbx]
0x180030dae  mov     rcx, rbx
0x180030db1  mov     rax, [rax+8]
0x180030db5  call    j__guard_dispatch_icall
0x180030dba  mov     eax, ebp
0x180030dbc  lock xadd [rdi+8], eax
0x180030dc1  add     eax, ebp
0x180030dc3  jnz     short loc_180030DED
0x180030dc5  mov     rax, [rdi]
0x180030dc8  mov     rcx, rdi
0x180030dcb  mov     rax, [rax]
0x180030dce  call    j__guard_dispatch_icall
0x180030dd3  mov     eax, ebp
0x180030dd5  lock xadd [rdi+0Ch], eax
0x180030dda  add     eax, ebp
0x180030ddc  jnz     short loc_180030DED
0x180030dde  mov     rax, [rdi]
0x180030de1  mov     rcx, rdi
0x180030de4  mov     rax, [rax+8]
0x180030de8  call    j__guard_dispatch_icall
0x180030ded  mov     eax, ebp
0x180030def  lock xadd [rsi+8], eax
0x180030df4  add     eax, ebp
0x180030df6  jnz     short loc_180030E20
0x180030df8  mov     rax, [rsi]
0x180030dfb  mov     rcx, rsi
0x180030dfe  mov     rax, [rax]
0x180030e01  call    j__guard_dispatch_icall
0x180030e06  mov     eax, ebp
0x180030e08  lock xadd [rsi+0Ch], eax
0x180030e0d  add     eax, ebp
0x180030e0f  jnz     short loc_180030E20
0x180030e11  mov     rax, [rsi]
0x180030e14  mov     rcx, rsi
0x180030e17  mov     rax, [rax+8]
0x180030e1b  call    j__guard_dispatch_icall
0x180030e20  sub     dword ptr cs:qword_1800AA688, r12d
0x180030e27  jnz     short loc_180030E33
0x180030e29  mov     dword ptr cs:qword_1800AA688+4, 0
0x180030e33  mov     rbx, 8000000000h
0x180030e3d  lea     rcx, CriticalSection; lpCriticalSection
0x180030e44  call    cs:LeaveCriticalSection
0x180030e4a  mov     rax, rbx
0x180030e4d  add     rsp, 58h
0x180030e51  pop     r14
0x180030e53  pop     r12
0x180030e55  pop     rdi
0x180030e56  pop     rsi
0x180030e57  pop     rbp
0x180030e58  pop     rbx
0x180030e59  retn
```
