# Windows::Compat::Inventory::MareDataWriter::CreateDataFiles(void)

- ea: `0x180017778`
- end: `0x180017982`
- name: `?CreateDataFiles@MareDataWriter@Inventory@Compat@Windows@@AEAAJXZ`
- size: `522`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::MareDataWriter *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800172a0`

## callees

- `0x180004ea0`
- `0x18000ff30`
- `0x180011fcc`
- `0x1800134b8`
- `0x180013ad4`
- `0x180017778`
- `0x18001de34`
- `0x180022364`
- `0x18004c020`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x180017880`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x180017880`

## string_xrefs

- `0x1800177e3`: `Windows::Compat::Inventory::MareDataWriter::CreateDataFiles`
- `0x1800178ff`: `Windows::Compat::Inventory::MareDataWriter::CreateDataFiles`
- `0x180017928`: `Windows::Compat::Inventory::MareDataWriter::CreateDataFiles`
- `0x18001791b`: `MareDataWrite::SetFileSecurity failed [%#x]`
- `0x1800178f2`: `_wfopen_s failed [%d]`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::MareDataWriter::CreateDataFiles(
        Windows::Compat::Inventory::MareDataWriter *this)
{
  int UserData; // eax
  unsigned int v3; // ebx
  __int64 i; // rdi
  __int64 v5; // r15
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rcx
  int v9; // eax
  const wchar_t *v10; // rdx
  errno_t v11; // eax
  __int64 v12; // r14
  FILE *Stream; // [rsp+30h] [rbp-89h] BYREF
  __int128 v15; // [rsp+38h] [rbp-81h] BYREF
  __int64 v16; // [rsp+48h] [rbp-71h]
  __int64 v17; // [rsp+50h] [rbp-69h]
  _BYTE *v18; // [rsp+58h] [rbp-61h]
  _BYTE v19[32]; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v20[32]; // [rsp+88h] [rbp-31h] BYREF
  wchar_t *FileName[4]; // [rsp+A8h] [rbp-11h] BYREF
  _BYTE v22[32]; // [rsp+C8h] [rbp+Fh] BYREF

  v15 = 0;
  v16 = 0;
  v17 = 0;
  UserData = Windows::Compat::Inventory::MareDataWriter::GetUserData(&v15, 0);
  v3 = UserData;
  if ( UserData >= 0 )
  {
    v5 = *((_QWORD *)&v15 + 1);
    for ( i = v15; ; i += 96 )
    {
      if ( i == v5 )
        goto LABEL_17;
      std::wstring::wstring(FileName, i);
      std::wstring::wstring(v22, i + 64);
      v18 = v19;
      v6 = std::wstring::wstring(v19, v22);
      v7 = std::wstring::wstring(v20, FileName);
      v9 = Windows::Compat::Inventory::MareDataWriter::SetFileSecurityW(v8, v7, v6);
      v3 = v9;
      if ( v9 < 0 )
        break;
      Stream = 0;
      v10 = (const wchar_t *)FileName;
      if ( FileName[3] > (wchar_t *)7 )
        v10 = FileName[0];
      v11 = _wfopen_s(&Stream, v10, L"a, ccs=UTF-8");
      if ( v11 )
      {
        AslLogCallPrintf(
          1,
          "Windows::Compat::Inventory::MareDataWriter::CreateDataFiles",
          696,
          "_wfopen_s failed [%d]",
          v11);
        v3 = -2147467259;
LABEL_16:
        std::wstring::~wstring(v22);
        std::wstring::~wstring(FileName);
        goto LABEL_17;
      }
      v12 = *((_QWORD *)this + 39);
      if ( v12 == *((_QWORD *)this + 40) )
      {
        std::vector<std::pair<std::wstring,_iobuf *>>::_Emplace_reallocate<std::wstring &,_iobuf * &>(
          (char *)this + 304,
          *((_QWORD *)this + 39),
          v22,
          &Stream);
      }
      else
      {
        std::wstring::wstring(*((_QWORD *)this + 39), v22);
        *(_QWORD *)(v12 + 32) = Stream;
        *((_QWORD *)this + 39) += 40LL;
      }
      std::wstring::~wstring(v22);
      std::wstring::~wstring(FileName);
    }
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareDataWriter::CreateDataFiles",
      688,
      "MareDataWrite::SetFileSecurity failed [%#x]",
      v9);
    goto LABEL_16;
  }
  AslLogCallPrintf(
    1,
    "Windows::Compat::Inventory::MareDataWriter::CreateDataFiles",
    676,
    "GetUserData failed [%#x]",
    UserData);
LABEL_17:
  std::vector<std::tuple<std::wstring,std::wstring,std::wstring>>::~vector<std::tuple<std::wstring,std::wstring,std::wstring>>(&v15);
  return v3;
}

```

## disassembly

```asm
0x180017778  mov     [rsp-8+arg_8], rbx
0x18001777d  mov     [rsp-8+arg_10], rsi
0x180017782  push    rbp
0x180017783  push    rdi
0x180017784  push    r13
0x180017786  push    r14
0x180017788  push    r15
0x18001778a  lea     rbp, [rsp-37h]
0x18001778f  sub     rsp, 0F0h
0x180017796  mov     rax, cs:__security_cookie
0x18001779d  xor     rax, rsp
0x1800177a0  mov     [rbp+57h+var_28], rax
0x1800177a4  mov     r13, rcx
0x1800177a7  xorps   xmm0, xmm0
0x1800177aa  movdqu  [rsp+110h+var_D8], xmm0
0x1800177b0  mov     [rbp+57h+var_C8], 0
0x1800177b8  mov     [rbp+57h+var_C0], 0
0x1800177c0  xor     edx, edx
0x1800177c2  lea     rcx, [rsp+110h+var_D8]
0x1800177c7  call    ?GetUserData@MareDataWriter@Inventory@Compat@Windows@@SAJAEAV?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@@2@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@@Z; Windows::Compat::Inventory::MareDataWriter::GetUserData(std::vector<std::tuple<std::wstring,std::wstring,std::wstring>> &,std::wstring *)
0x1800177cc  mov     ebx, eax
0x1800177ce  test    eax, eax
0x1800177d0  jns     short loc_1800177F9
0x1800177d2  mov     [rsp+110h+var_F0], eax
0x1800177d6  lea     r9, aGetuserdataFai; "GetUserData failed [%#x]"
0x1800177dd  mov     r8d, 2A4h
0x1800177e3  lea     rdx, aWindowsCompatI_7; "Windows::Compat::Inventory::MareDataWri"...
0x1800177ea  mov     ecx, 1
0x1800177ef  call    AslLogCallPrintf
0x1800177f4  jmp     loc_18001794E
0x1800177f9  mov     rdi, qword ptr [rsp+110h+var_D8]
0x1800177fe  mov     r15, qword ptr [rbp+57h+var_D8+8]
0x180017802  jmp     loc_1800178E3
0x180017807  mov     rdx, rdi
0x18001780a  lea     rcx, [rbp+57h+FileName]
0x18001780e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017813  nop
0x180017814  lea     rdx, [rdi+40h]
0x180017818  lea     rcx, [rbp+57h+var_48]
0x18001781c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017821  nop
0x180017822  lea     rax, [rbp+57h+var_A8]
0x180017826  mov     [rbp+57h+var_B8], rax
0x18001782a  lea     rdx, [rbp+57h+var_48]
0x18001782e  lea     rcx, [rbp+57h+var_A8]
0x180017832  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017837  mov     rbx, rax
0x18001783a  lea     rdx, [rbp+57h+FileName]
0x18001783e  lea     rcx, [rbp+57h+var_88]
0x180017842  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017847  nop
0x180017848  mov     r8, rbx
0x18001784b  mov     rdx, rax
0x18001784e  call    ?SetFileSecurityW@MareDataWriter@Inventory@Compat@Windows@@AEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Compat::Inventory::MareDataWriter::SetFileSecurityW(std::wstring,std::wstring)
0x180017853  mov     ebx, eax
0x180017855  test    eax, eax
0x180017857  js      loc_180017917
0x18001785d  mov     [rsp+110h+Stream], 0
0x180017866  lea     rdx, [rbp+57h+FileName]
0x18001786a  cmp     [rbp+57h+var_50], 7
0x18001786f  cmova   rdx, [rbp+57h+FileName]; FileName
0x180017874  lea     r8, aACcsUtf8; "a, ccs=UTF-8"
0x18001787b  lea     rcx, [rsp+110h+Stream]; Stream
0x180017880  call    cs:__imp__wfopen_s
0x180017886  test    eax, eax
0x180017888  jnz     short loc_1800178EE
0x18001788a  lea     rsi, [r13+130h]
0x180017891  mov     r14, [rsi+8]
0x180017895  cmp     r14, [rsi+10h]
0x180017899  jz      short loc_1800178B7
0x18001789b  lea     rdx, [rbp+57h+var_48]
0x18001789f  mov     rcx, r14
0x1800178a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800178a7  mov     rax, [rsp+110h+Stream]
0x1800178ac  mov     [r14+20h], rax
0x1800178b0  add     qword ptr [rsi+8], 28h ; '('
0x1800178b5  jmp     short loc_1800178CC
0x1800178b7  lea     r9, [rsp+110h+Stream]
0x1800178bc  lea     r8, [rbp+57h+var_48]
0x1800178c0  mov     rdx, r14
0x1800178c3  mov     rcx, rsi
0x1800178c6  call    ??$_Emplace_reallocate@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAPEAU_iobuf@@@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_iobuf@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_iobuf@@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_iobuf@@@1@QEAU21@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAPEAU_iobuf@@@Z; std::vector<std::pair<std::wstring,_iobuf *>>::_Emplace_reallocate<std::wstring &,_iobuf * &>(std::pair<std::wstring,_iobuf *> * const,std::wstring &,_iobuf * &)
0x1800178cb  nop
0x1800178cc  lea     rcx, [rbp+57h+var_48]
0x1800178d0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800178d5  nop
0x1800178d6  lea     rcx, [rbp+57h+FileName]
0x1800178da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800178df  add     rdi, 60h ; '`'
0x1800178e3  cmp     rdi, r15
0x1800178e6  jnz     loc_180017807
0x1800178ec  jmp     short loc_18001794E
0x1800178ee  mov     [rsp+110h+var_F0], eax
0x1800178f2  lea     r9, aWfopenSFailedD; "_wfopen_s failed [%d]"
0x1800178f9  mov     r8d, 2B8h
0x1800178ff  lea     rdx, aWindowsCompatI_7; "Windows::Compat::Inventory::MareDataWri"...
0x180017906  mov     ecx, 1
0x18001790b  call    AslLogCallPrintf
0x180017910  mov     ebx, 80004005h
0x180017915  jmp     short loc_18001793A
0x180017917  mov     [rsp+110h+var_F0], eax
0x18001791b  lea     r9, aMaredatawriteS; "MareDataWrite::SetFileSecurity failed ["...
0x180017922  mov     r8d, 2B0h
0x180017928  lea     rdx, aWindowsCompatI_7; "Windows::Compat::Inventory::MareDataWri"...
0x18001792f  mov     ecx, 1
0x180017934  call    AslLogCallPrintf
0x180017939  nop
0x18001793a  lea     rcx, [rbp+57h+var_48]
0x18001793e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017943  nop
0x180017944  lea     rcx, [rbp+57h+FileName]
0x180017948  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001794d  nop
0x18001794e  lea     rcx, [rsp+110h+var_D8]
0x180017953  call    ??1?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@@2@@std@@QEAA@XZ; std::vector<std::tuple<std::wstring,std::wstring,std::wstring>>::~vector<std::tuple<std::wstring,std::wstring,std::wstring>>(void)
0x180017958  mov     eax, ebx
0x18001795a  mov     rcx, [rbp+57h+var_28]
0x18001795e  xor     rcx, rsp; StackCookie
0x180017961  call    __security_check_cookie
0x180017966  lea     r11, [rsp+110h+var_20]
0x18001796e  mov     rbx, [r11+38h]
0x180017972  mov     rsi, [r11+40h]
0x180017976  mov     rsp, r11
0x180017979  pop     r15
0x18001797b  pop     r14
0x18001797d  pop     r13
0x18001797f  pop     rdi
0x180017980  pop     rbp
0x180017981  retn
```
