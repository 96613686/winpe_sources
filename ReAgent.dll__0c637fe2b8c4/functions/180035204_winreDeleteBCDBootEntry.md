# winreDeleteBCDBootEntry

- ea: `0x180035204`
- end: `0x1800352f9`
- name: `winreDeleteBCDBootEntry`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180023b50`

## callees

- `0x1800059fc`
- `0x180035204`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800352dc`
- `ntdll!RtlNtStatusToDosError` at `0x1800352dc`
- `bcd!BcdDeleteElement` at `0x180035279`
- `bcd!BcdDeleteElement` at `0x180035279`
- `bcd!BcdCloseStore` at `0x1800352bc`
- `bcd!BcdCloseStore` at `0x1800352bc`
- `bcd!BcdCloseObject` at `0x1800352a3`
- `bcd!BcdCloseObject` at `0x1800352a3`
- `bcd!BcdOpenObject` at `0x18003525a`
- `bcd!BcdOpenObject` at `0x18003525a`
- `bcd!BcdOpenStore` at `0x180035234`
- `bcd!BcdOpenStore` at `0x180035234`

## string_xrefs

- `0x180035266`: `BcdOpenObject failed: 0x%x`
- `0x180035240`: `Open store failed: 0x%x`
- `0x180035285`: `BcdDeleteElement failed: 0x%x`

## pseudocode

```c
ULONG winreDeleteBCDBootEntry()
{
  int v0; // eax
  NTSTATUS v1; // ebx
  int v2; // eax
  int v3; // eax
  __int64 v5; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+28h] [rbp-20h] BYREF

  v6 = 0;
  v5 = 0;
  v0 = BcdOpenStore(0, 0, &v6);
  v1 = v0;
  if ( v0 >= 0 )
  {
    v2 = BcdOpenObject(v6, &GUID_WINDOWS_BOOTMGR, &v5);
    v1 = v2;
    if ( v2 >= 0 )
    {
      v3 = BcdDeleteElement(v5, 603979778);
      v1 = v3;
      if ( v3 < 0 )
        UnattendLogW(1, L"BcdDeleteElement failed: 0x%x", (unsigned int)v3);
    }
    else
    {
      UnattendLogW(1, L"BcdOpenObject failed: 0x%x", (unsigned int)v2);
    }
  }
  else
  {
    UnattendLogW(1, L"Open store failed: 0x%x", (unsigned int)v0);
  }
  if ( v5 )
  {
    BcdCloseObject();
    v5 = 0;
  }
  if ( v6 )
    BcdCloseStore();
  if ( v1 >= 0 )
    return 0;
  UnattendLogW(1, L"winreSetBCDBootEntry failed: 0x%x", (unsigned int)v1);
  return RtlNtStatusToDosError(v1);
}

```

## disassembly

```asm
0x180035204  push    rbx
0x180035206  sub     rsp, 40h
0x18003520a  mov     rax, cs:__security_cookie
0x180035211  xor     rax, rsp
0x180035214  mov     [rsp+48h+var_18], rax
0x180035219  lea     r8, [rsp+48h+var_20]
0x18003521e  mov     [rsp+48h+var_20], 0
0x180035227  xor     edx, edx
0x180035229  mov     [rsp+48h+var_28], 0
0x180035232  xor     ecx, ecx
0x180035234  call    cs:__imp_BcdOpenStore
0x18003523a  mov     ebx, eax
0x18003523c  test    eax, eax
0x18003523e  jns     short loc_180035249
0x180035240  lea     rdx, aOpenStoreFaile; "Open store failed: 0x%x"
0x180035247  jmp     short loc_18003528C
0x180035249  mov     rcx, [rsp+48h+var_20]
0x18003524e  lea     r8, [rsp+48h+var_28]
0x180035253  lea     rdx, GUID_WINDOWS_BOOTMGR
0x18003525a  call    cs:__imp_BcdOpenObject
0x180035260  mov     ebx, eax
0x180035262  test    eax, eax
0x180035264  jns     short loc_18003526F
0x180035266  lea     rdx, aBcdopenobjectF_0; "BcdOpenObject failed: 0x%x"
0x18003526d  jmp     short loc_18003528C
0x18003526f  mov     rcx, [rsp+48h+var_28]
0x180035274  mov     edx, 24000002h
0x180035279  call    cs:__imp_BcdDeleteElement
0x18003527f  mov     ebx, eax
0x180035281  test    eax, eax
0x180035283  jns     short loc_180035299
0x180035285  lea     rdx, aBcddeleteeleme_0; "BcdDeleteElement failed: 0x%x"
0x18003528c  mov     r8d, eax
0x18003528f  mov     ecx, 1
0x180035294  call    UnattendLogW
0x180035299  mov     rcx, [rsp+48h+var_28]
0x18003529e  test    rcx, rcx
0x1800352a1  jz      short loc_1800352B2
0x1800352a3  call    cs:__imp_BcdCloseObject
0x1800352a9  mov     [rsp+48h+var_28], 0
0x1800352b2  mov     rcx, [rsp+48h+var_20]
0x1800352b7  test    rcx, rcx
0x1800352ba  jz      short loc_1800352C2
0x1800352bc  call    cs:__imp_BcdCloseStore
0x1800352c2  test    ebx, ebx
0x1800352c4  jns     short loc_1800352E4
0x1800352c6  mov     r8d, ebx
0x1800352c9  lea     rdx, aWinresetbcdboo_0; "winreSetBCDBootEntry failed: 0x%x"
0x1800352d0  mov     ecx, 1
0x1800352d5  call    UnattendLogW
0x1800352da  mov     ecx, ebx; Status
0x1800352dc  call    cs:__imp_RtlNtStatusToDosError
0x1800352e2  jmp     short loc_1800352E6
0x1800352e4  xor     eax, eax
0x1800352e6  mov     rcx, [rsp+48h+var_18]
0x1800352eb  xor     rcx, rsp; StackCookie
0x1800352ee  call    __security_check_cookie
0x1800352f3  add     rsp, 40h
0x1800352f7  pop     rbx
0x1800352f8  retn
```
