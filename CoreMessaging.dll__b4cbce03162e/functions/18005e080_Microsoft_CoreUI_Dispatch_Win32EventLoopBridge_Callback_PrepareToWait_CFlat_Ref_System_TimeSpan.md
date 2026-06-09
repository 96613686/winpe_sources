# Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::Callback_PrepareToWait(CFlat::Ref<System::TimeSpan>)

- ea: `0x18005e080`
- end: `0x18005e2ea`
- name: `?Callback_PrepareToWait@Win32EventLoopBridge@Dispatch@CoreUI@Microsoft@@UEAA_NU?$Ref@UTimeSpan@System@@@CFlat@@@Z`
- size: `618`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000ec10`
- `0x180010ed0`
- `0x18005e080`
- `0x18005e2f0`
- `0x18008d418`
- `0x18008e39c`
- `0x18008ee90`
- `0x1800a61cc`
- `0x1800a623c`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005e1a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005e1a1`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18005e1ad`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18005e1ad`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18005e1c3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18005e1c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_BOOL8 __fastcall Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::Callback_PrepareToWait(__int64 a1, __int64 *a2)
{
  __int64 v3; // rsi
  __int64 v4; // rbp
  int v5; // r14d
  __int64 v6; // rcx
  bool v7; // bl
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r15
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  HANDLE CurrentThread; // rbp
  int ThreadPriority; // edi
  int v18; // edx
  __int64 v19; // rdx
  unsigned __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // [rsp+60h] [rbp+8h] BYREF
  __int64 v23; // [rsp+68h] [rbp+10h] BYREF
  __int64 v24; // [rsp+70h] [rbp+18h] BYREF
  __int64 v25; // [rsp+78h] [rbp+20h]

  v3 = *(_QWORD *)(a1 + 40);
  v24 = v3;
  if ( v3 )
    ++*(_DWORD *)(v3 + 16);
  if ( *(_DWORD *)(v3 + 112) != 0x7FFFFFFF )
  {
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    v18 = *(_DWORD *)(v3 + 112);
    if ( ThreadPriority < v18 )
    {
      if ( SetThreadPriority(CurrentThread, v18) )
        *(_DWORD *)(v3 + 116) = ThreadPriority;
    }
  }
  v4 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 80) + 32LL) + 56LL);
  v5 = *(_DWORD *)(v4 + 60);
  v25 = v4;
  if ( v4 )
    ++*(_DWORD *)(v4 + 16);
  if ( !*(_QWORD *)(v4 + 80) )
  {
    v6 = 0x7FFFFFFFFFFFFFFFLL;
    goto LABEL_8;
  }
  System::DateTime::get_UtcNow(&v23);
  v9 = v23;
  v10 = System::DateTime::ToFileTimeUtc((System::DateTime *)&v23);
  v23 = v10;
  v22 = v10;
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x10) != 0 )
    McTemplateU0tx_EventWriteTransfer((unsigned int)v10, v11, 0, (unsigned int)v10 | v23 & 0xFFFFFFFF00000000uLL);
  v12 = *(_QWORD *)(v4 + 80);
  v23 = v12;
  if ( v12 )
  {
    v13 = *(_DWORD *)(v12 + 16);
    if ( v13 > 0 )
      *(_DWORD *)(v12 + 16) = v13 + 1;
  }
  if ( *(_DWORD *)(v12 + 24) == 1 )
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64 *))(v12 + 40))(*(_QWORD *)(v12 + 48), 0, &v22);
  else
    CFlat::DelegateImpl<Microsoft::CoreUI::Dispatch::DispatchCallback,0,void (bool,CFlat::Ref<Microsoft::CoreUI::Dispatch::FILETIME>),long (void *,bool,_FILETIME *),0>::MulticastInvoke(
      v12,
      0,
      &v22);
  if ( v12 )
    System::Object::Release$((System::Object *)v12);
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x10) != 0 )
    McTemplateU0x_EventWriteTransfer(v15, v14, v22);
  System::DateTime::get_UtcNow(&v24);
  v23 = v22;
  System::DateTime::FromFileTimeUtc(&v23, v22);
  v19 = v23;
  *(_QWORD *)(v4 + 88) = v23;
  v20 = v19 & 0x3FFFFFFFFFFFFFFFLL;
  v6 = v20 - (v9 & 0x3FFFFFFFFFFFFFFFLL);
  if ( v6 <= 0 || v20 >= 0x2BCA2875F4373FFFLL )
  {
    *(_QWORD *)(v4 + 88) = 0x2BCA2875F4373FFFLL;
    v6 = 0x7FFFFFFFFFFFFFFFLL;
LABEL_33:
    *(_QWORD *)(v4 + 96) = v6;
    goto LABEL_8;
  }
  v21 = v20 - (v24 & 0x3FFFFFFFFFFFFFFFLL);
  *(_QWORD *)(v4 + 96) = v21;
  if ( v21 > v6 )
    goto LABEL_33;
  if ( v21 >= 0 )
  {
    v6 = v21;
  }
  else
  {
    *(_QWORD *)(v4 + 96) = 0;
    v6 = 0;
  }
LABEL_8:
  *a2 = v6;
  if ( v4 )
    System::Object::ReleaseNotFrozen$((System::Object *)v4);
  v7 = !*(_BYTE *)(v3 + 70) && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 80) + 32LL) + 56LL) + 60LL) == v5;
  if ( v3 )
    System::Object::ReleaseNotFrozen$((System::Object *)v3);
  return v7;
}

```

## disassembly

```asm
0x18005e080  push    rbx
0x18005e082  push    rbp
0x18005e083  push    rsi
0x18005e084  push    rdi
0x18005e085  push    r14
0x18005e087  push    r15
0x18005e089  sub     rsp, 28h
0x18005e08d  mov     rbx, rdx
0x18005e090  mov     rsi, [rcx+28h]
0x18005e094  mov     [rsp+58h+arg_10], rsi
0x18005e099  test    rsi, rsi
0x18005e09c  jz      short loc_18005E0A1
0x18005e09e  inc     dword ptr [rsi+10h]
0x18005e0a1  cmp     dword ptr [rsi+70h], 7FFFFFFFh
0x18005e0a8  jnz     loc_18005E1A1
0x18005e0ae  mov     rax, [rsi+50h]
0x18005e0b2  mov     rcx, [rax+20h]
0x18005e0b6  mov     rbp, [rcx+38h]
0x18005e0ba  mov     r14d, [rbp+3Ch]
0x18005e0be  mov     [rsp+58h+arg_18], rbp
0x18005e0c3  test    rbp, rbp
0x18005e0c6  jz      short loc_18005E0CB
0x18005e0c8  inc     dword ptr [rbp+10h]
0x18005e0cb  cmp     qword ptr [rbp+50h], 0
0x18005e0d0  jnz     short loc_18005E12B
0x18005e0d2  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18005e0dc  mov     [rbx], rcx
0x18005e0df  test    rbp, rbp
0x18005e0e2  jz      short loc_18005E0EC
0x18005e0e4  mov     rcx, rbp; this
0x18005e0e7  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18005e0ec  cmp     byte ptr [rsi+46h], 0
0x18005e0f0  jnz     loc_18005E2E2
0x18005e0f6  mov     rax, [rsi+50h]
0x18005e0fa  mov     rcx, [rax+20h]
0x18005e0fe  mov     rax, [rcx+38h]
0x18005e102  cmp     [rax+3Ch], r14d
0x18005e106  jnz     loc_18005E2E2
0x18005e10c  mov     bl, 1
0x18005e10e  test    rsi, rsi
0x18005e111  jz      short loc_18005E11B
0x18005e113  mov     rcx, rsi; this
0x18005e116  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18005e11b  movzx   eax, bl
0x18005e11e  add     rsp, 28h
0x18005e122  pop     r15
0x18005e124  pop     r14
0x18005e126  pop     rdi
0x18005e127  pop     rsi
0x18005e128  pop     rbp
0x18005e129  pop     rbx
0x18005e12a  retn
0x18005e12b  lea     rcx, [rsp+58h+arg_8]
0x18005e130  call    ?get_UtcNow@DateTime@System@@SA?AU12@XZ; System::DateTime::get_UtcNow(void)
0x18005e135  mov     rdi, [rsp+58h+arg_8]
0x18005e13a  mov     [rsp+58h+arg_8], rdi
0x18005e13f  lea     rcx, [rsp+58h+arg_8]; this
0x18005e144  call    ?ToFileTimeUtc@DateTime@System@@QEBA_JXZ; System::DateTime::ToFileTimeUtc(void)
0x18005e149  mov     rcx, rax
0x18005e14c  shr     rcx, 20h
0x18005e150  mov     dword ptr [rsp+58h+arg_8+4], ecx
0x18005e154  mov     dword ptr [rsp+58h+arg_8], eax
0x18005e158  mov     dword ptr [rsp+58h+arg_0], eax
0x18005e15c  mov     dword ptr [rsp+58h+arg_0+4], ecx
0x18005e160  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 10h
0x18005e167  jnz     loc_18005E29C
0x18005e16d  mov     r15, [rbp+50h]
0x18005e171  mov     [rsp+58h+arg_8], r15
0x18005e176  test    r15, r15
0x18005e179  jz      short loc_18005E189
0x18005e17b  mov     eax, [r15+10h]
0x18005e17f  test    eax, eax
0x18005e181  jle     short loc_18005E189
0x18005e183  inc     eax
0x18005e185  mov     [r15+10h], eax
0x18005e189  lea     r8, [rsp+58h+arg_0]
0x18005e18e  xor     edx, edx
0x18005e190  cmp     dword ptr [r15+18h], 1
0x18005e195  jz      short loc_18005E1D9
0x18005e197  mov     rcx, r15
0x18005e19a  call    ?MulticastInvoke@?$DelegateImpl@VDispatchCallback@Dispatch@CoreUI@Microsoft@@$0A@$$A6AX_NU?$Ref@UFILETIME@Dispatch@CoreUI@Microsoft@@@CFlat@@@Z$$A6AJPEAX0PEAU_FILETIME@@@Z$0A@@CFlat@@AEBAX_NU?$Ref@UFILETIME@Dispatch@CoreUI@Microsoft@@@2@@Z; CFlat::DelegateImpl<Microsoft::CoreUI::Dispatch::DispatchCallback,0,void (bool,CFlat::Ref<Microsoft::CoreUI::Dispatch::FILETIME>),long (void *,bool,_FILETIME *),0>::MulticastInvoke(bool,CFlat::Ref<Microsoft::CoreUI::Dispatch::FILETIME>)
0x18005e19f  jmp     short loc_18005E1E7
0x18005e1a1  call    cs:__imp_GetCurrentThread
0x18005e1a7  mov     rbp, rax
0x18005e1aa  mov     rcx, rax; hThread
0x18005e1ad  call    cs:__imp_GetThreadPriority
0x18005e1b3  mov     edi, eax
0x18005e1b5  mov     edx, [rsi+70h]; nPriority
0x18005e1b8  cmp     eax, edx
0x18005e1ba  jge     loc_18005E0AE
0x18005e1c0  mov     rcx, rbp; hThread
0x18005e1c3  call    cs:__imp_SetThreadPriority
0x18005e1c9  test    eax, eax
0x18005e1cb  jz      loc_18005E0AE
0x18005e1d1  mov     [rsi+74h], edi
0x18005e1d4  jmp     loc_18005E0AE
0x18005e1d9  mov     rcx, [r15+30h]
0x18005e1dd  mov     rax, [r15+28h]
0x18005e1e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e1e6  nop
0x18005e1e7  test    r15, r15
0x18005e1ea  jz      short loc_18005E1F4
0x18005e1ec  mov     rcx, r15; this
0x18005e1ef  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18005e1f4  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 10h
0x18005e1fb  jnz     loc_18005E2C0
0x18005e201  lea     rcx, [rsp+58h+arg_10]
0x18005e206  call    ?get_UtcNow@DateTime@System@@SA?AU12@XZ; System::DateTime::get_UtcNow(void)
0x18005e20b  mov     ecx, dword ptr [rsp+58h+arg_0]
0x18005e20f  mov     eax, dword ptr [rsp+58h+arg_0+4]
0x18005e213  mov     dword ptr [rsp+58h+arg_8+4], eax
0x18005e217  mov     dword ptr [rsp+58h+arg_8], ecx
0x18005e21b  mov     rdx, [rsp+58h+arg_8]
0x18005e220  lea     rcx, [rsp+58h+arg_8]
0x18005e225  call    ?FromFileTimeUtc@DateTime@System@@SA?AU12@_J@Z; System::DateTime::FromFileTimeUtc(__int64)
0x18005e22a  mov     rdx, [rsp+58h+arg_8]
0x18005e22f  mov     [rbp+58h], rdx
0x18005e233  mov     r8, 3FFFFFFFFFFFFFFFh
0x18005e23d  and     rdx, r8
0x18005e240  and     rdi, r8
0x18005e243  mov     rcx, rdx
0x18005e246  sub     rcx, rdi
0x18005e249  mov     rax, 2BCA2875F4373FFFh
0x18005e253  test    rcx, rcx
0x18005e256  jg      short loc_18005E26F
0x18005e258  mov     [rbp+58h], rax
0x18005e25c  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18005e266  mov     [rbp+60h], rcx
0x18005e26a  jmp     loc_18005E0DC
0x18005e26f  cmp     rdx, rax
0x18005e272  jnb     short loc_18005E258
0x18005e274  mov     rax, [rsp+58h+arg_10]
0x18005e279  and     rax, r8
0x18005e27c  sub     rdx, rax
0x18005e27f  mov     [rbp+60h], rdx
0x18005e283  cmp     rdx, rcx
0x18005e286  jg      short loc_18005E266
0x18005e288  test    rdx, rdx
0x18005e28b  jns     short loc_18005E2DA
0x18005e28d  mov     qword ptr [rbp+60h], 0
0x18005e295  xor     ecx, ecx
0x18005e297  jmp     loc_18005E0DC
0x18005e29c  mov     r9, [rsp+58h+arg_8]
0x18005e2a1  mov     rcx, 0FFFFFFFF00000000h
0x18005e2ab  and     r9, rcx
0x18005e2ae  mov     ecx, eax
0x18005e2b0  or      r9, rcx
0x18005e2b3  xor     r8d, r8d
0x18005e2b6  call    McTemplateU0tx_EventWriteTransfer
0x18005e2bb  jmp     loc_18005E16D
0x18005e2c0  mov     r8d, dword ptr [rsp+58h+arg_0+4]
0x18005e2c5  shl     r8, 20h
0x18005e2c9  mov     eax, dword ptr [rsp+58h+arg_0]
0x18005e2cd  or      r8, rax
0x18005e2d0  call    McTemplateU0x_EventWriteTransfer
0x18005e2d5  jmp     loc_18005E201
0x18005e2da  mov     rcx, rdx
0x18005e2dd  jmp     loc_18005E0DC
0x18005e2e2  xor     bl, bl
0x18005e2e4  jmp     loc_18005E10E
```
