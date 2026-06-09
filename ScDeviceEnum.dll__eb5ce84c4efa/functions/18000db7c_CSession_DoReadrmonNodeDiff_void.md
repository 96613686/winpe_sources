# CSession::_DoReadrmonNodeDiff(void)

- ea: `0x18000db7c`
- end: `0x18000dd55`
- name: `?_DoReadrmonNodeDiff@CSession@@AEAAJXZ`
- size: `473`
- prototype: `__int64 __fastcall(CSession *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18000e160`

## callees

- `0x180001444`
- `0x180001610`
- `0x1800080dc`
- `0x18000c558`
- `0x18000c58c`
- `0x18000c804`
- `0x18000c954`
- `0x18000cdb4`
- `0x18000d604`
- `0x18000d9cc`
- `0x18000db20`
- `0x18000db7c`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dce0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dd05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dce0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dd05`

## string_xrefs

- `0x18000dbb0`: `CSession::_DoReadrmonNodeDiff`

## pseudocode

```c
__int64 __fastcall CSession::_DoReadrmonNodeDiff(CSession *this)
{
  __int64 v2; // rcx
  _QWORD *v3; // rsi
  void *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rbx
  _QWORD *i; // rdi
  int v9; // ebx
  __int64 result; // rax
  unsigned int v11; // ebx
  int v12; // [rsp+20h] [rbp-98h] BYREF
  int v13; // [rsp+24h] [rbp-94h] BYREF
  _QWORD *v14; // [rsp+28h] [rbp-90h] BYREF
  void *v15; // [rsp+30h] [rbp-88h] BYREF
  _QWORD *v16; // [rsp+38h] [rbp-80h] BYREF
  __int64 v17; // [rsp+40h] [rbp-78h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-70h] BYREF
  _QWORD v19[3]; // [rsp+50h] [rbp-68h] BYREF
  char v20[32]; // [rsp+68h] [rbp-50h] BYREF

  v12 = 0;
  v13 = 0;
  strcpy(v20, "CSession::_DoReadrmonNodeDiff");
  v19[0] = v20;
  v19[1] = &v13;
  v19[2] = &v12;
  lambda_5b6d62c85ffc47d26f2cbfe8972de3f6_::operator()(v19);
  try
  {
    v13 = 1;
    v14 = v19;
    v16 = 0;
    v7 = 0;
    v17 = 0;
    v3 = std::_List_alloc<0,std::_List_base_types<std::unique_ptr<CInformationNode>>>::_Buynode0(v2, 0, 0);
    v16 = v3;
    Microsoft::WRL::Wrappers::CriticalSection::Lock(&lpCriticalSection, (char *)this + 80);
    for ( i = (_QWORD *)*((_QWORD *)this + 18); i; i = (_QWORD *)i[30] )
    {
      v4 = operator new(0x20u);
      v15 = v4;
      if ( v4 )
        v4 = (void *)std::wstring::wstring(v4, *i);
      v15 = v4;
      v6 = std::_List_buy<std::unique_ptr<std::wstring>>::_Buynode<std::unique_ptr<std::wstring>>(
             v5,
             (__int64)v3,
             v3[1],
             (__int64 *)&v15);
      if ( v7 == 0xAAAAAAAAAAAAAA9LL )
        std::_Xlength_error("list<T> too long");
      v17 = ++v7;
      v3[1] = v6;
      **(_QWORD **)(v6 + 8) = v6;
      std::unique_ptr<std::wstring>::_Delete(&v15, v6);
    }
    v9 = CSession::DoNodeDiff(this, &v16);
    v12 = v9;
    if ( v9 >= 0 )
    {
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      std::list<std::unique_ptr<std::wstring>>::~list<std::unique_ptr<std::wstring>>((__int64)&v16);
      v11 = v12;
      WppTraceUnwinder__lambda_5b6d62c85ffc47d26f2cbfe8972de3f6____::_WppTraceUnwinder__lambda_5b6d62c85ffc47d26f2cbfe8972de3f6____(&v14);
      result = v11;
    }
    else
    {
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      std::list<std::unique_ptr<std::wstring>>::~list<std::unique_ptr<std::wstring>>((__int64)&v16);
      WppTraceUnwinder__lambda_5b6d62c85ffc47d26f2cbfe8972de3f6____::_WppTraceUnwinder__lambda_5b6d62c85ffc47d26f2cbfe8972de3f6____(&v14);
      result = (unsigned int)v9;
    }
  }
  catch ( std::bad_alloc )
  {
    v12 = -2147024882;
    WppTraceUnwinder__lambda_5b6d62c85ffc47d26f2cbfe8972de3f6____::_WppTraceUnwinder__lambda_5b6d62c85ffc47d26f2cbfe8972de3f6____(&v14);
    return 2147942414LL;
  }
  v13 = 1;
}

```

## disassembly

```asm
0x18000db7c  mov     r11, rsp
0x18000db7f  push    rbx
0x18000db80  push    rsi
0x18000db81  push    rdi
0x18000db82  push    r14
0x18000db84  sub     rsp, 98h
0x18000db8b  mov     rax, cs:__security_cookie
0x18000db92  xor     rax, rsp
0x18000db95  mov     [rsp+0B8h+var_30], rax
0x18000db9d  mov     r14, rcx
0x18000dba0  mov     [rsp+0B8h+var_98], 0
0x18000dba8  mov     [rsp+0B8h+var_94], 0
0x18000dbb0  movups  xmm0, xmmword ptr cs:aCsessionDoread; "CSession::_DoReadrmonNodeDiff"
0x18000dbb7  movups  xmmword ptr [rsp+0B8h+var_50], xmm0
0x18000dbbc  movups  xmm1, xmmword ptr cs:aCsessionDoread+0Eh; "eadrmonNodeDiff"
0x18000dbc3  movups  xmmword ptr [rsp+0B8h+var_50+0Eh], xmm1
0x18000dbc8  lea     rax, [r11-50h]
0x18000dbcc  mov     [r11-68h], rax
0x18000dbd0  lea     rax, [rsp+0B8h+var_94]
0x18000dbd5  mov     [r11-60h], rax
0x18000dbd9  lea     rax, [rsp+0B8h+var_98]
0x18000dbde  mov     [r11-58h], rax
0x18000dbe2  lea     rcx, [r11-68h]
0x18000dbe6  call    _lambda_5b6d62c85ffc47d26f2cbfe8972de3f6___operator__
0x18000dbeb  mov     [rsp+0B8h+var_94], 1
0x18000dbf3  lea     rax, [rsp+0B8h+var_68]
0x18000dbf8  mov     [rsp+0B8h+var_90], rax
0x18000dbfd  mov     [rsp+0B8h+var_80], 0
0x18000dc06  xor     ebx, ebx
0x18000dc08  mov     [rsp+0B8h+var_78], rbx
0x18000dc0d  xor     r8d, r8d
0x18000dc10  xor     edx, edx
0x18000dc12  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@V?$allocator@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@@2@@std@@@std@@QEAAPEAU?$_List_node@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<std::unique_ptr<CInformationNode>>>::_Buynode0(std::_List_node<std::unique_ptr<CInformationNode>,void *> *,std::_List_node<std::unique_ptr<CInformationNode>,void *> *)
0x18000dc17  mov     rsi, rax
0x18000dc1a  mov     [rsp+0B8h+var_80], rax
0x18000dc1f  lea     rdx, [r14+50h]
0x18000dc23  lea     rcx, [rsp+0B8h+lpCriticalSection]
0x18000dc28  call    ?Lock@CriticalSection@Wrappers@WRL@Microsoft@@SA?AVSyncLockCriticalSection@Details@234@PEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::CriticalSection::Lock(_RTL_CRITICAL_SECTION *)
0x18000dc2d  nop
0x18000dc2e  mov     rdi, [r14+90h]
0x18000dc35  test    rdi, rdi
0x18000dc38  jz      loc_18000DCBF
0x18000dc3e  mov     ecx, 20h ; ' '; Size
0x18000dc43  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dc48  mov     [rsp+0B8h+var_88], rax
0x18000dc4d  test    rax, rax
0x18000dc50  jz      short loc_18000DC5E
0x18000dc52  mov     rdx, [rdi]
0x18000dc55  mov     rcx, rax
0x18000dc58  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000dc5d  nop
0x18000dc5e  mov     [rsp+0B8h+var_88], rax
0x18000dc63  lea     r9, [rsp+0B8h+var_88]
0x18000dc68  mov     r8, [rsi+8]
0x18000dc6c  mov     rdx, rsi
0x18000dc6f  call    ??$_Buynode@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@?$_List_buy@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAX@1@PEAU21@0$$QEAV?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@1@@Z; std::_List_buy<std::unique_ptr<std::wstring>>::_Buynode<std::unique_ptr<std::wstring>>(std::_List_node<std::unique_ptr<std::wstring>,void *> *,std::_List_node<std::unique_ptr<std::wstring>,void *> *,std::unique_ptr<std::wstring> &&)
0x18000dc74  mov     rdx, rax
0x18000dc77  mov     rcx, 0AAAAAAAAAAAAAA9h
0x18000dc81  sub     rcx, rbx
0x18000dc84  cmp     rcx, 1
0x18000dc88  jnb     short loc_18000DC96
0x18000dc8a  lea     rcx, aListTTooLong; "list<T> too long"
0x18000dc91  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000dc96  inc     rbx
0x18000dc99  mov     [rsp+0B8h+var_78], rbx
0x18000dc9e  mov     [rsi+8], rdx
0x18000dca2  mov     rax, [rax+8]
0x18000dca6  mov     [rax], rdx
0x18000dca9  lea     rcx, [rsp+0B8h+var_88]
0x18000dcae  call    ?_Delete@?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::wstring>::_Delete(void)
0x18000dcb3  mov     rdi, [rdi+0F0h]
0x18000dcba  jmp     loc_18000DC35
0x18000dcbf  lea     rdx, [rsp+0B8h+var_80]
0x18000dcc4  mov     rcx, r14
0x18000dcc7  call    ?DoNodeDiff@CSession@@QEAAJAEAV?$list@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@@Z; CSession::DoNodeDiff(std::list<std::unique_ptr<std::wstring>> &)
0x18000dccc  mov     ebx, eax
0x18000dcce  mov     [rsp+0B8h+var_98], eax
0x18000dcd2  mov     rcx, [rsp+0B8h+lpCriticalSection]; lpCriticalSection
0x18000dcd7  test    eax, eax
0x18000dcd9  jns     short loc_18000DD00
0x18000dcdb  test    rcx, rcx
0x18000dcde  jz      short loc_18000DCE7
0x18000dce0  call    cs:__imp_LeaveCriticalSection
0x18000dce6  nop
0x18000dce7  lea     rcx, [rsp+0B8h+var_80]
0x18000dcec  call    ??1?$list@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::list<std::unique_ptr<std::wstring>>::~list<std::unique_ptr<std::wstring>>(void)
0x18000dcf1  nop
0x18000dcf2  lea     rcx, [rsp+0B8h+var_90]
0x18000dcf7  call    WppTraceUnwinder__lambda_5b6d62c85ffc47d26f2cbfe8972de3f6_______WppTraceUnwinder__lambda_5b6d62c85ffc47d26f2cbfe8972de3f6____
0x18000dcfc  mov     eax, ebx
0x18000dcfe  jmp     short loc_18000DD38
0x18000dd00  test    rcx, rcx
0x18000dd03  jz      short loc_18000DD0C
0x18000dd05  call    cs:__imp_LeaveCriticalSection
0x18000dd0b  nop
0x18000dd0c  lea     rcx, [rsp+0B8h+var_80]
0x18000dd11  call    ??1?$list@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::list<std::unique_ptr<std::wstring>>::~list<std::unique_ptr<std::wstring>>(void)
0x18000dd16  nop
0x18000dd17  mov     ebx, [rsp+0B8h+var_98]
0x18000dd1b  lea     rcx, [rsp+0B8h+var_90]
0x18000dd20  call    WppTraceUnwinder__lambda_5b6d62c85ffc47d26f2cbfe8972de3f6_______WppTraceUnwinder__lambda_5b6d62c85ffc47d26f2cbfe8972de3f6____
0x18000dd25  mov     eax, ebx
0x18000dd27  jmp     short loc_18000DD38
0x18000dd29  lea     rcx, [rsp+0B8h+var_90]
0x18000dd2e  call    WppTraceUnwinder__lambda_5b6d62c85ffc47d26f2cbfe8972de3f6_______WppTraceUnwinder__lambda_5b6d62c85ffc47d26f2cbfe8972de3f6____
0x18000dd33  mov     eax, 8007000Eh
0x18000dd38  mov     rcx, [rsp+0B8h+var_30]
0x18000dd40  xor     rcx, rsp; StackCookie
0x18000dd43  call    __security_check_cookie
0x18000dd48  add     rsp, 98h
0x18000dd4f  pop     r14
0x18000dd51  pop     rdi
0x18000dd52  pop     rsi
0x18000dd53  pop     rbx
0x18000dd54  retn
```
