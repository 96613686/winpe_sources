# CCellularSmsDevice::GetSmscNumber(ushort * *)

- ea: `0x180045110`
- end: `0x18004535b`
- name: `?GetSmscNumber@CCellularSmsDevice@@UEAAJPEAPEAG@Z`
- size: `587`
- prototype: `__int64 __fastcall(CCellularSmsDevice *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task`

## callees

- `0x180003a90`
- `0x180003f50`
- `0x18000dd64`
- `0x180045110`
- `0x180048640`
- `0x180051420`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045199`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045199`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180045251`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180045251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800451a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800451a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045269`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800452a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800452a9`
- `OLEAUT32!__imp_SysFreeString` at `0x18004531c`
- `OLEAUT32!__imp_SysFreeString` at `0x18004531c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCellularSmsDevice::GetSmscNumber(CCellularSmsDevice *this, unsigned __int16 **a2)
{
  int v4; // ebp
  HANDLE *v5; // rdi
  HANDLE *v6; // r12
  char *v7; // rsi
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v10; // ebx
  char *v11; // rbp
  DWORD v12; // eax
  signed int v13; // eax
  const wchar_t *v14; // rax
  _BYTE v16[16]; // [rsp+40h] [rbp-38h] BYREF
  HANDLE *v17; // [rsp+88h] [rbp+10h] BYREF

  if ( !a2 )
  {
    v4 = -2147024809;
    LODWORD(v5) = 0;
LABEL_20:
    v14 = (const wchar_t *)((char *)this + 176);
    if ( *((_QWORD *)this + 25) > 7u )
      v14 = *(const wchar_t **)v14;
    LogSmsRouterError(
      "CCellularSmsDevice::GetSmscNumber",
      0x3AFu,
      v4,
      "GetSmscAddress DeviceId: %S, Context 0x%08X failed",
      v14,
      (_DWORD)v5);
    if ( a2 )
    {
      if ( *a2 )
      {
        SysFreeString(*a2);
        *a2 = 0;
      }
    }
    return (unsigned int)v4;
  }
  *a2 = 0;
  v5 = (HANDLE *)operator new(0x18u);
  v6 = v5;
  v17 = v5;
  *(_OWORD *)v5 = 0;
  v5[2] = 0;
  v7 = (char *)this + 112;
  (**((void (__fastcall ***)(char *))this + 14))((char *)this + 112);
  EventW = CreateEventW(0, 0, 0, 0);
  *v5 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this + 112);
    v11 = (char *)this + 928;
    goto LABEL_15;
  }
  v5[2] = a2;
  if ( *((_DWORD *)this + 22) && *((_QWORD *)this + 20) )
  {
    v11 = (char *)this + 928;
    std::_Tree<std::_Tset_traits<SmsServiceCallContext *,std::less<SmsServiceCallContext *>,std::allocator<SmsServiceCallContext *>,0>>::insert<0,0>(
      (__int64 *)this + 116,
      (__int64)v16,
      (__int64 *)&v17);
    v6 = v17;
    v5 = v17;
    (*(void (__fastcall **)(_QWORD, char *, HANDLE *))(**((_QWORD **)this + 20) + 32LL))(
      *((_QWORD *)this + 20),
      (char *)this + 32,
      v17);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this + 112);
    v12 = WaitForSingleObject(*v6, 0x3A980u);
    if ( v12 )
    {
      if ( v12 == 258 )
      {
        v10 = -2147023436;
      }
      else
      {
        v13 = GetLastError();
        v10 = v13;
        if ( v13 > 0 )
          v10 = (unsigned __int16)v13 | 0x80070000;
      }
    }
    else
    {
      v10 = 0;
    }
LABEL_15:
    (**(void (__fastcall ***)(char *))v7)((char *)this + 112);
    std::_Tree<std::_Tset_traits<SmsServiceCallContext *,std::less<SmsServiceCallContext *>,std::allocator<SmsServiceCallContext *>,0>>::erase(
      v11,
      &v17);
    if ( *v6 )
      CloseHandle(*v6);
    v4 = *((_DWORD *)v5 + 2);
    if ( v4 >= 0 )
      v4 = v10;
    operator delete(v6);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this + 112);
    if ( v4 >= 0 )
      return (unsigned int)v4;
    goto LABEL_20;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this + 112);
  return 2147947423LL;
}

```

## disassembly

```asm
0x180045110  mov     [rsp+arg_0], rbx
0x180045115  mov     [rsp+arg_10], rbp
0x18004511a  push    rsi
0x18004511b  push    rdi
0x18004511c  push    r12
0x18004511e  push    r14
0x180045120  push    r15
0x180045122  sub     rsp, 50h
0x180045126  mov     r14, rdx
0x180045129  mov     r15, rcx
0x18004512c  test    rdx, rdx
0x18004512f  jnz     short loc_18004513D
0x180045131  mov     ebp, 80070057h
0x180045136  xor     edi, edi
0x180045138  jmp     loc_1800452D9
0x18004513d  mov     qword ptr [rdx], 0
0x180045144  mov     ecx, 18h; Size
0x180045149  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004514e  mov     rdi, rax
0x180045151  mov     r12, rax
0x180045154  mov     [rsp+78h+arg_8], rax
0x18004515c  xorps   xmm0, xmm0
0x18004515f  xor     eax, eax
0x180045161  movups  xmmword ptr [r12], xmm0
0x180045166  mov     [r12+10h], rax
0x18004516b  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180045172  mov     [rsp+78h+var_48], rax
0x180045177  lea     rsi, [r15+70h]
0x18004517b  mov     [rsp+78h+var_40], rsi
0x180045180  mov     rax, [rsi]
0x180045183  mov     rcx, rsi
0x180045186  mov     rax, [rax]
0x180045189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004518e  nop
0x18004518f  xor     r9d, r9d; lpName
0x180045192  xor     r8d, r8d; bInitialState
0x180045195  xor     edx, edx; bManualReset
0x180045197  xor     ecx, ecx; lpEventAttributes
0x180045199  call    cs:__imp_CreateEventW
0x18004519f  mov     [r12], rax
0x1800451a3  test    rax, rax
0x1800451a6  jnz     short loc_1800451D9
0x1800451a8  call    cs:__imp_GetLastError
0x1800451ae  mov     ebx, eax
0x1800451b0  test    eax, eax
0x1800451b2  jle     short loc_1800451BD
0x1800451b4  movzx   ebx, ax
0x1800451b7  or      ebx, 80070000h
0x1800451bd  mov     rax, [rsi]
0x1800451c0  mov     rcx, rsi
0x1800451c3  mov     rax, [rax+8]
0x1800451c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451cc  nop
0x1800451cd  lea     rbp, [r15+3A0h]
0x1800451d4  jmp     loc_180045282
0x1800451d9  mov     [rdi+10h], r14
0x1800451dd  cmp     dword ptr [r15+58h], 0
0x1800451e2  jz      loc_18004532D
0x1800451e8  cmp     qword ptr [r15+0A0h], 0
0x1800451f0  jz      loc_18004532D
0x1800451f6  lea     rbp, [r15+3A0h]
0x1800451fd  lea     r8, [rsp+78h+arg_8]
0x180045205  lea     rdx, [rsp+78h+var_38]
0x18004520a  mov     rcx, rbp
0x18004520d  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@PEAUSmsServiceCallContext@@U?$less@PEAUSmsServiceCallContext@@@std@@V?$allocator@PEAUSmsServiceCallContext@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAUSmsServiceCallContext@@@std@@@std@@@std@@_N@1@AEBQEAUSmsServiceCallContext@@@Z; std::_Tree<std::_Tset_traits<SmsServiceCallContext *,std::less<SmsServiceCallContext *>,std::allocator<SmsServiceCallContext *>,0>>::insert<0,0>(SmsServiceCallContext * const &)
0x180045212  mov     rcx, [r15+0A0h]
0x180045219  mov     r12, [rsp+78h+arg_8]
0x180045221  mov     rdi, r12
0x180045224  mov     rax, [rcx]
0x180045227  lea     rdx, [r15+20h]
0x18004522b  mov     r8, r12
0x18004522e  mov     rax, [rax+20h]
0x180045232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045237  nop
0x180045238  mov     rax, [rsi]
0x18004523b  mov     rcx, rsi
0x18004523e  mov     rax, [rax+8]
0x180045242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045247  nop
0x180045248  mov     edx, 3A980h; dwMilliseconds
0x18004524d  mov     rcx, [r12]; hHandle
0x180045251  call    cs:__imp_WaitForSingleObject
0x180045257  test    eax, eax
0x180045259  jz      short loc_180045280
0x18004525b  cmp     eax, 102h
0x180045260  jnz     short loc_180045269
0x180045262  mov     ebx, 800705B4h
0x180045267  jmp     short loc_180045282
0x180045269  call    cs:__imp_GetLastError
0x18004526f  mov     ebx, eax
0x180045271  test    eax, eax
0x180045273  jle     short loc_180045282
0x180045275  movzx   ebx, ax
0x180045278  or      ebx, 80070000h
0x18004527e  jmp     short loc_180045282
0x180045280  xor     ebx, ebx
0x180045282  mov     rax, [rsi]
0x180045285  mov     rcx, rsi
0x180045288  mov     rax, [rax]
0x18004528b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045290  lea     rdx, [rsp+78h+arg_8]
0x180045298  mov     rcx, rbp
0x18004529b  call    ?erase@?$_Tree@V?$_Tset_traits@PEAUSmsServiceCallContext@@U?$less@PEAUSmsServiceCallContext@@@std@@V?$allocator@PEAUSmsServiceCallContext@@@3@$0A@@std@@@std@@QEAA_KAEBQEAUSmsServiceCallContext@@@Z; std::_Tree<std::_Tset_traits<SmsServiceCallContext *,std::less<SmsServiceCallContext *>,std::allocator<SmsServiceCallContext *>,0>>::erase(SmsServiceCallContext * const &)
0x1800452a0  mov     rcx, [r12]; hObject
0x1800452a4  test    rcx, rcx
0x1800452a7  jz      short loc_1800452AF
0x1800452a9  call    cs:__imp_CloseHandle
0x1800452af  mov     ebp, [rdi+8]
0x1800452b2  test    ebp, ebp
0x1800452b4  cmovns  ebp, ebx
0x1800452b7  mov     edx, 18h
0x1800452bc  mov     rcx, r12; Block
0x1800452bf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800452c4  nop
0x1800452c5  mov     rax, [rsi]
0x1800452c8  mov     rcx, rsi
0x1800452cb  mov     rax, [rax+8]
0x1800452cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800452d4  nop
0x1800452d5  test    ebp, ebp
0x1800452d7  jns     short loc_180045329
0x1800452d9  lea     rax, [r15+0B0h]
0x1800452e0  cmp     qword ptr [rax+18h], 7
0x1800452e5  jbe     short loc_1800452EA
0x1800452e7  mov     rax, [rax]
0x1800452ea  mov     [rsp+78h+var_50], rdi
0x1800452ef  mov     [rsp+78h+var_58], rax
0x1800452f4  lea     r9, aGetsmscaddress; "GetSmscAddress DeviceId: %S, Context 0x"...
0x1800452fb  mov     r8d, ebp; int
0x1800452fe  mov     edx, 3AFh; unsigned int
0x180045303  lea     rcx, aCcellularsmsde_8; "CCellularSmsDevice::GetSmscNumber"
0x18004530a  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18004530f  test    r14, r14
0x180045312  jz      short loc_180045329
0x180045314  mov     rcx, [r14]; bstrString
0x180045317  test    rcx, rcx
0x18004531a  jz      short loc_180045329
0x18004531c  call    cs:__imp_SysFreeString
0x180045322  mov     qword ptr [r14], 0
0x180045329  mov     eax, ebp
0x18004532b  jmp     short loc_180045342
0x18004532d  mov     rax, [rsi]
0x180045330  mov     rcx, rsi
0x180045333  mov     rax, [rax+8]
0x180045337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004533c  nop
0x18004533d  mov     eax, 8007139Fh
0x180045342  lea     r11, [rsp+78h+var_28]
0x180045347  mov     rbx, [r11+30h]
0x18004534b  mov     rbp, [r11+40h]
0x18004534f  mov     rsp, r11
0x180045352  pop     r15
0x180045354  pop     r14
0x180045356  pop     r12
0x180045358  pop     rdi
0x180045359  pop     rsi
0x18004535a  retn
```
