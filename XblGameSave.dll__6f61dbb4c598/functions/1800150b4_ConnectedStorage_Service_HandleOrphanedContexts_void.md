# ConnectedStorage::Service::HandleOrphanedContexts(void)

- ea: `0x1800150b4`
- end: `0x1800151fa`
- name: `?HandleOrphanedContexts@Service@ConnectedStorage@@AEAAXXZ`
- size: `326`
- prototype: `void __fastcall(ConnectedStorage::Service *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180019530`

## callees

- `0x180003c70`
- `0x180011b94`
- `0x180011bd0`
- `0x180012f7c`
- `0x180014cf8`
- `0x1800150b4`
- `0x180015a4c`
- `0x18001bf48`
- `0x18001c040`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001519f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001519f`
- `ntdll!RtlIsMultiSessionSku` at `0x1800150df`
- `ntdll!RtlIsMultiSessionSku` at `0x1800150df`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ConnectedStorage::Service::HandleOrphanedContexts(ConnectedStorage::Service *this)
{
  HSTRING *v2; // r15
  __int64 v3; // r14
  __int64 i; // rbx
  HSTRING *v5; // rdi
  HSTRING string; // [rsp+20h] [rbp-B8h] BYREF
  HSTRING newString[2]; // [rsp+28h] [rbp-B0h] BYREF
  __int64 v8; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v9; // [rsp+40h] [rbp-98h]
  _QWORD v10[4]; // [rsp+50h] [rbp-88h] BYREF
  _BYTE v11[64]; // [rsp+70h] [rbp-68h] BYREF

  if ( !(unsigned __int8)RtlIsMultiSessionSku() )
  {
    try
    {
      ConnectedStorage::Service::GetAllContexts(this);
      (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 10) + 56LL))(*((_QWORD *)this + 10), &v8);
      v5 = (HSTRING *)v10[0];
      v2 = (HSTRING *)v10[1];
      while ( v5 != v2 )
      {
        ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(newString, *v5);
        ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, newString);
        newString[1] = (HSTRING)&string;
        v3 = v9;
        for ( i = v8; i != v3 && !(unsigned __int8)ConnectedStorage::SimpleHStringWrapper::operator==(i, &string); i += 8 )
          ;
        WindowsDeleteString(string);
        string = 0;
        if ( i == v9 )
          ConnectedStorage::Service::OnUserDeletedEvent(
            this,
            (const struct ConnectedStorage::SimpleHStringWrapper *)newString);
        WindowsDeleteString(newString[0]);
        newString[0] = 0;
        v5 += 7;
      }
      std::vector<ConnectedStorage::SimpleHStringWrapper>::_Tidy(&v8);
      std::vector<XblGameSaveProviderInfo>::_Tidy(v10);
    }
    catch ( ConnectedStorage::ComError v11 )
    {
      ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v11);
      return;
    }
    catch ( std::bad_alloc )
    {
      return;
    }
    catch ( ... )
    {
    }
  }
}

```

## disassembly

```asm
0x1800150b4  mov     [rsp+arg_8], rbx
0x1800150b9  mov     [rsp+arg_10], rsi
0x1800150be  push    rdi
0x1800150bf  push    r14
0x1800150c1  push    r15
0x1800150c3  sub     rsp, 0C0h
0x1800150ca  mov     rax, cs:__security_cookie
0x1800150d1  xor     rax, rsp
0x1800150d4  mov     [rsp+0D8h+var_28], rax
0x1800150dc  mov     rsi, rcx
0x1800150df  call    cs:__imp_RtlIsMultiSessionSku
0x1800150e5  test    al, al
0x1800150e7  jnz     loc_1800151CD
0x1800150ed  lea     rdx, [rsp+0D8h+var_88]
0x1800150f2  mov     rcx, rsi; struct ConnectedStorage::Mutex *
0x1800150f5  call    ?GetAllContexts@Service@ConnectedStorage@@QEAA?AV?$vector@UXblGameSaveProviderInfo@@V?$allocator@UXblGameSaveProviderInfo@@@std@@@std@@XZ; ConnectedStorage::Service::GetAllContexts(void)
0x1800150fa  nop
0x1800150fb  mov     rcx, [rsi+50h]
0x1800150ff  mov     rax, [rcx]
0x180015102  lea     rdx, [rsp+0D8h+var_A0]
0x180015107  mov     rax, [rax+38h]
0x18001510b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015110  nop
0x180015111  mov     rdi, [rsp+0D8h+var_88]
0x180015116  mov     r15, [rsp+0D8h+var_80]
0x18001511b  cmp     rdi, r15
0x18001511e  jz      loc_1800151B7
0x180015124  mov     rdx, [rdi]; string
0x180015127  lea     rcx, [rsp+0D8h+newString]; newString
0x18001512c  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x180015131  nop
0x180015132  lea     rdx, [rsp+0D8h+newString]; struct ConnectedStorage::SimpleHStringWrapper *
0x180015137  lea     rcx, [rsp+0D8h+string]; newString
0x18001513c  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x180015141  lea     rax, [rsp+0D8h+string]
0x180015146  mov     [rsp+0D8h+var_A8], rax
0x18001514b  mov     r14, [rsp+0D8h+var_98]
0x180015150  mov     rbx, [rsp+0D8h+var_A0]
0x180015155  cmp     rbx, r14
0x180015158  jz      short loc_180015171
0x18001515a  lea     rdx, [rsp+0D8h+string]
0x18001515f  mov     rcx, rbx
0x180015162  call    ??8SimpleHStringWrapper@ConnectedStorage@@QEBA_NAEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator==(ConnectedStorage::SimpleHStringWrapper const &)
0x180015167  test    al, al
0x180015169  jnz     short loc_180015171
0x18001516b  add     rbx, 8
0x18001516f  jmp     short loc_180015155
0x180015171  mov     rcx, [rsp+0D8h+string]; string
0x180015176  call    cs:__imp_WindowsDeleteString
0x18001517c  mov     [rsp+0D8h+string], 0
0x180015185  cmp     rbx, [rsp+0D8h+var_98]
0x18001518a  jnz     short loc_18001519A
0x18001518c  lea     rdx, [rsp+0D8h+newString]; struct ConnectedStorage::SimpleHStringWrapper *
0x180015191  mov     rcx, rsi; this
0x180015194  call    ?OnUserDeletedEvent@Service@ConnectedStorage@@AEAAXAEBVSimpleHStringWrapper@2@@Z; ConnectedStorage::Service::OnUserDeletedEvent(ConnectedStorage::SimpleHStringWrapper const &)
0x180015199  nop
0x18001519a  mov     rcx, [rsp+0D8h+newString]; string
0x18001519f  call    cs:__imp_WindowsDeleteString
0x1800151a5  mov     [rsp+0D8h+newString], 0
0x1800151ae  add     rdi, 38h ; '8'
0x1800151b2  jmp     loc_18001511B
0x1800151b7  lea     rcx, [rsp+0D8h+var_A0]
0x1800151bc  call    ?_Tidy@?$vector@VSimpleHStringWrapper@ConnectedStorage@@V?$allocator@VSimpleHStringWrapper@ConnectedStorage@@@std@@@std@@AEAAXXZ; std::vector<ConnectedStorage::SimpleHStringWrapper>::_Tidy(void)
0x1800151c1  nop
0x1800151c2  lea     rcx, [rsp+0D8h+var_88]
0x1800151c7  call    ?_Tidy@?$vector@UXblGameSaveProviderInfo@@V?$allocator@UXblGameSaveProviderInfo@@@std@@@std@@AEAAXXZ; std::vector<XblGameSaveProviderInfo>::_Tidy(void)
0x1800151cc  nop
0x1800151cd  mov     rcx, [rsp+0D8h+var_28]
0x1800151d5  xor     rcx, rsp; StackCookie
0x1800151d8  call    __security_check_cookie
0x1800151dd  lea     r11, [rsp+0D8h+var_18]
0x1800151e5  mov     rbx, [r11+28h]
0x1800151e9  mov     rsi, [r11+30h]
0x1800151ed  mov     rsp, r11
0x1800151f0  pop     r15
0x1800151f2  pop     r14
0x1800151f4  pop     rdi
0x1800151f5  retn
0x1800151f6  jmp     short loc_1800151CD
0x1800151f8  jmp     short loc_1800151CD
```
