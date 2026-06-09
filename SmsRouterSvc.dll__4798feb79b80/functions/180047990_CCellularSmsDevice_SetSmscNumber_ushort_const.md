# CCellularSmsDevice::SetSmscNumber(ushort const *)

- ea: `0x180047990`
- end: `0x180047c21`
- name: `?SetSmscNumber@CCellularSmsDevice@@UEAAJPEBG@Z`
- size: `657`
- prototype: `int(CCellularSmsDevice *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x180003f50`
- `0x180004998`
- `0x18000dd64`
- `0x1800320b0`
- `0x180047990`
- `0x180048640`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180047a45`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180047a45`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180047b1f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180047b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047a53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047a53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047b37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047b73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047b73`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCellularSmsDevice::SetSmscNumber(CCellularSmsDevice *this, const unsigned __int16 *a2)
{
  _QWORD *v4; // r15
  char *v5; // rsi
  HANDLE EventW; // rax
  signed int v7; // eax
  unsigned int v8; // ebx
  char *v9; // r14
  __int64 v10; // rbp
  const wchar_t *v11; // rdi
  const wchar_t *v12; // r9
  DWORD v13; // eax
  signed int LastError; // eax
  int v15; // r14d
  __int64 v17[3]; // [rsp+40h] [rbp-278h] BYREF
  _BYTE v18[24]; // [rsp+58h] [rbp-260h] BYREF
  _BYTE v19[528]; // [rsp+70h] [rbp-248h] BYREF

  memset_0(v19, 0, 0x204u);
  SetSmsAddressFromString(a2, (struct SMS_ADDRESS *)v19);
  v4 = operator new(0x18u);
  v17[0] = (__int64)v4;
  *(_OWORD *)v4 = 0;
  v4[2] = 0;
  v17[1] = (__int64)&Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v5 = (char *)this + 112;
  v17[2] = (__int64)this + 112;
  (**((void (__fastcall ***)(char *))this + 14))((char *)this + 112);
  if ( *((_DWORD *)this + 22) && *((_QWORD *)this + 20) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *v4 = EventW;
    if ( EventW )
    {
      v9 = (char *)this + 912;
      std::_Tree<std::_Tset_traits<SmsServiceCallContext *,std::less<SmsServiceCallContext *>,std::allocator<SmsServiceCallContext *>,0>>::insert<0,0>(
        (__int64 *)this + 114,
        (__int64)v18,
        v17);
      v4 = (_QWORD *)v17[0];
      v10 = v17[0];
      (*(void (__fastcall **)(_QWORD, char *, _BYTE *, __int64))(**((_QWORD **)this + 20) + 40LL))(
        *((_QWORD *)this + 20),
        (char *)this + 56,
        v19,
        v17[0]);
      v11 = (const wchar_t *)((char *)this + 176);
      if ( *((_QWORD *)v11 + 3) <= 7u )
        v12 = v11;
      else
        v12 = *(const wchar_t **)v11;
      LogSmsRouterInfo(
        "CCellularSmsDevice::SetSmscNumber",
        0x33Fu,
        "SetSmscAddress DeviceId: %S, Address: %S, Context: 0x%08X",
        v12,
        a2,
        (_DWORD)v4);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 8LL))(v5);
      v13 = WaitForSingleObject((HANDLE)*v4, 0x3A980u);
      if ( v13 )
      {
        if ( v13 == 258 )
        {
          v8 = -2147023436;
        }
        else
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      else
      {
        v8 = 0;
      }
    }
    else
    {
      v7 = GetLastError();
      v8 = v7;
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 8LL))((char *)this + 112);
      v9 = (char *)this + 912;
      v10 = (__int64)v4;
      v11 = (const wchar_t *)((char *)this + 176);
    }
    (**(void (__fastcall ***)(char *))v5)(v5);
    std::_Tree<std::_Tset_traits<SmsServiceCallContext *,std::less<SmsServiceCallContext *>,std::allocator<SmsServiceCallContext *>,0>>::erase(
      v9,
      v17);
    if ( *v4 )
      CloseHandle((HANDLE)*v4);
    v15 = *(_DWORD *)(v10 + 8);
    if ( v15 >= 0 )
      v15 = v8;
    operator delete(v4);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 8LL))(v5);
    if ( v15 < 0 )
    {
      if ( *((_QWORD *)v11 + 3) > 7u )
        v11 = *(const wchar_t **)v11;
      LogSmsRouterError(
        "CCellularSmsDevice::SetSmscNumber",
        0x359u,
        v15,
        "SetSmscAddress DeviceId: %S, Address: %S, Context: 0x%08X failed",
        v11,
        a2,
        v10);
    }
    return (unsigned int)v15;
  }
  else
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 8LL))((char *)this + 112);
    return 2147947423LL;
  }
}

```

## disassembly

```asm
0x180047990  mov     [rsp+arg_10], rbx
0x180047995  mov     [rsp+arg_18], rbp
0x18004799a  push    rsi
0x18004799b  push    rdi
0x18004799c  push    r12
0x18004799e  push    r14
0x1800479a0  push    r15
0x1800479a2  sub     rsp, 290h
0x1800479a9  mov     rax, cs:__security_cookie
0x1800479b0  xor     rax, rsp
0x1800479b3  mov     [rsp+2B8h+var_38], rax
0x1800479bb  mov     r12, rdx
0x1800479be  mov     rdi, rcx
0x1800479c1  xor     edx, edx; Val
0x1800479c3  mov     r8d, 204h; Size
0x1800479c9  lea     rcx, [rsp+2B8h+var_248]; void *
0x1800479ce  call    memset_0
0x1800479d3  lea     rdx, [rsp+2B8h+var_248]; struct SMS_ADDRESS *
0x1800479d8  mov     rcx, r12; unsigned __int16 *
0x1800479db  call    ?SetSmsAddressFromString@@YAXPEBGPEAUSMS_ADDRESS@@@Z; SetSmsAddressFromString(ushort const *,SMS_ADDRESS *)
0x1800479e0  mov     ecx, 18h; Size
0x1800479e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800479ea  mov     r15, rax
0x1800479ed  mov     [rsp+2B8h+var_278], rax
0x1800479f2  xorps   xmm0, xmm0
0x1800479f5  xor     eax, eax
0x1800479f7  movups  xmmword ptr [r15], xmm0
0x1800479fb  mov     [r15+10h], rax
0x1800479ff  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180047a06  mov     [rsp+2B8h+var_270], rax
0x180047a0b  lea     rsi, [rdi+70h]
0x180047a0f  mov     [rsp+2B8h+var_268], rsi
0x180047a14  mov     rax, [rsi]
0x180047a17  mov     rcx, rsi
0x180047a1a  mov     rax, [rax]
0x180047a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a22  nop
0x180047a23  cmp     dword ptr [rdi+58h], 0
0x180047a27  jz      loc_180047BE0
0x180047a2d  cmp     qword ptr [rdi+0A0h], 0
0x180047a35  jz      loc_180047BE0
0x180047a3b  xor     r9d, r9d; lpName
0x180047a3e  xor     r8d, r8d; bInitialState
0x180047a41  xor     edx, edx; bManualReset
0x180047a43  xor     ecx, ecx; lpEventAttributes
0x180047a45  call    cs:__imp_CreateEventW
0x180047a4b  mov     [r15], rax
0x180047a4e  test    rax, rax
0x180047a51  jnz     short loc_180047A8E
0x180047a53  call    cs:__imp_GetLastError
0x180047a59  mov     ebx, eax
0x180047a5b  test    eax, eax
0x180047a5d  jle     short loc_180047A68
0x180047a5f  movzx   ebx, ax
0x180047a62  or      ebx, 80070000h
0x180047a68  mov     rax, [rsi]
0x180047a6b  mov     rcx, rsi
0x180047a6e  mov     rax, [rax+8]
0x180047a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a77  nop
0x180047a78  lea     r14, [rdi+390h]
0x180047a7f  mov     rbp, r15
0x180047a82  add     rdi, 0B0h
0x180047a89  jmp     loc_180047B50
0x180047a8e  lea     r14, [rdi+390h]
0x180047a95  lea     r8, [rsp+2B8h+var_278]
0x180047a9a  lea     rdx, [rsp+2B8h+var_260]
0x180047a9f  mov     rcx, r14
0x180047aa2  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@PEAUSmsServiceCallContext@@U?$less@PEAUSmsServiceCallContext@@@std@@V?$allocator@PEAUSmsServiceCallContext@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAUSmsServiceCallContext@@@std@@@std@@@std@@_N@1@AEBQEAUSmsServiceCallContext@@@Z; std::_Tree<std::_Tset_traits<SmsServiceCallContext *,std::less<SmsServiceCallContext *>,std::allocator<SmsServiceCallContext *>,0>>::insert<0,0>(SmsServiceCallContext * const &)
0x180047aa7  mov     rcx, [rdi+0A0h]
0x180047aae  mov     r15, [rsp+2B8h+var_278]
0x180047ab3  mov     rbp, r15
0x180047ab6  mov     rax, [rcx]
0x180047ab9  lea     rdx, [rdi+38h]
0x180047abd  mov     r9, r15
0x180047ac0  lea     r8, [rsp+2B8h+var_248]
0x180047ac5  mov     rax, [rax+28h]
0x180047ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ace  add     rdi, 0B0h
0x180047ad5  cmp     qword ptr [rdi+18h], 7
0x180047ada  jbe     short loc_180047AE1
0x180047adc  mov     r9, [rdi]
0x180047adf  jmp     short loc_180047AE4
0x180047ae1  mov     r9, rdi
0x180047ae4  mov     [rsp+2B8h+var_290], r15
0x180047ae9  mov     [rsp+2B8h+var_298], r12
0x180047aee  lea     r8, aSetsmscaddress_2; "SetSmscAddress DeviceId: %S, Address: %"...
0x180047af5  mov     edx, 33Fh; unsigned int
0x180047afa  lea     rcx, aCcellularsmsde_3; "CCellularSmsDevice::SetSmscNumber"
0x180047b01  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180047b06  nop
0x180047b07  mov     rax, [rsi]
0x180047b0a  mov     rcx, rsi
0x180047b0d  mov     rax, [rax+8]
0x180047b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b16  nop
0x180047b17  mov     edx, 3A980h; dwMilliseconds
0x180047b1c  mov     rcx, [r15]; hHandle
0x180047b1f  call    cs:__imp_WaitForSingleObject
0x180047b25  test    eax, eax
0x180047b27  jz      short loc_180047B4E
0x180047b29  cmp     eax, 102h
0x180047b2e  jnz     short loc_180047B37
0x180047b30  mov     ebx, 800705B4h
0x180047b35  jmp     short loc_180047B50
0x180047b37  call    cs:__imp_GetLastError
0x180047b3d  mov     ebx, eax
0x180047b3f  test    eax, eax
0x180047b41  jle     short loc_180047B50
0x180047b43  movzx   ebx, ax
0x180047b46  or      ebx, 80070000h
0x180047b4c  jmp     short loc_180047B50
0x180047b4e  xor     ebx, ebx
0x180047b50  mov     rax, [rsi]
0x180047b53  mov     rcx, rsi
0x180047b56  mov     rax, [rax]
0x180047b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b5e  lea     rdx, [rsp+2B8h+var_278]
0x180047b63  mov     rcx, r14
0x180047b66  call    ?erase@?$_Tree@V?$_Tset_traits@PEAUSmsServiceCallContext@@U?$less@PEAUSmsServiceCallContext@@@std@@V?$allocator@PEAUSmsServiceCallContext@@@3@$0A@@std@@@std@@QEAA_KAEBQEAUSmsServiceCallContext@@@Z; std::_Tree<std::_Tset_traits<SmsServiceCallContext *,std::less<SmsServiceCallContext *>,std::allocator<SmsServiceCallContext *>,0>>::erase(SmsServiceCallContext * const &)
0x180047b6b  mov     rcx, [r15]; hObject
0x180047b6e  test    rcx, rcx
0x180047b71  jz      short loc_180047B79
0x180047b73  call    cs:__imp_CloseHandle
0x180047b79  mov     r14d, [rbp+8]
0x180047b7d  test    r14d, r14d
0x180047b80  cmovns  r14d, ebx
0x180047b84  mov     edx, 18h
0x180047b89  mov     rcx, r15; Block
0x180047b8c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180047b91  nop
0x180047b92  mov     rax, [rsi]
0x180047b95  mov     rcx, rsi
0x180047b98  mov     rax, [rax+8]
0x180047b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ba1  nop
0x180047ba2  test    r14d, r14d
0x180047ba5  jns     short loc_180047BDB
0x180047ba7  cmp     qword ptr [rdi+18h], 7
0x180047bac  jbe     short loc_180047BB1
0x180047bae  mov     rdi, [rdi]
0x180047bb1  mov     [rsp+2B8h+var_288], rbp
0x180047bb6  mov     [rsp+2B8h+var_290], r12
0x180047bbb  mov     [rsp+2B8h+var_298], rdi
0x180047bc0  lea     r9, aSetsmscaddress; "SetSmscAddress DeviceId: %S, Address: %"...
0x180047bc7  mov     r8d, r14d; int
0x180047bca  mov     edx, 359h; unsigned int
0x180047bcf  lea     rcx, aCcellularsmsde_3; "CCellularSmsDevice::SetSmscNumber"
0x180047bd6  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180047bdb  mov     eax, r14d
0x180047bde  jmp     short loc_180047BF5
0x180047be0  mov     rax, [rsi]
0x180047be3  mov     rcx, rsi
0x180047be6  mov     rax, [rax+8]
0x180047bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047bef  nop
0x180047bf0  mov     eax, 8007139Fh
0x180047bf5  mov     rcx, [rsp+2B8h+var_38]
0x180047bfd  xor     rcx, rsp; StackCookie
0x180047c00  call    __security_check_cookie
0x180047c05  lea     r11, [rsp+2B8h+var_28]
0x180047c0d  mov     rbx, [r11+40h]
0x180047c11  mov     rbp, [r11+48h]
0x180047c15  mov     rsp, r11
0x180047c18  pop     r15
0x180047c1a  pop     r14
0x180047c1c  pop     r12
0x180047c1e  pop     rdi
0x180047c1f  pop     rsi
0x180047c20  retn
```
