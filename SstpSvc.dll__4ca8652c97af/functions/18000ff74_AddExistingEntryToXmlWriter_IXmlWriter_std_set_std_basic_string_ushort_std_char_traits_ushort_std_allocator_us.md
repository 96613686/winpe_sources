# AddExistingEntryToXmlWriter(IXmlWriter *,std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_lessstr,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>)

- ea: `0x18000ff74`
- end: `0x1800101d5`
- name: `?AddExistingEntryToXmlWriter@@YAKPEAUIXmlWriter@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `609`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800138c0`
- `0x180014490`

## callees

- `0x180007c34`
- `0x18000827c`
- `0x180008360`
- `0x18000f8fc`
- `0x18000fb00`
- `0x18000ff74`
- `0x180012560`
- `0x180012e20`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001d010`

## string_xrefs

- `0x180010136`: `AddExistingEntryToXmlWriter: WriteStartElement of IXmlWriter object failed with error %d`
- `0x180010124`: `AddExistingEntryToXmlWriter: WriteString of IXmlWriter object failed with error %d`
- `0x180010112`: `AddExistingEntryToXmlWriter: WriteFullEndElement of IXmlWriter object failed with error %d`

## pseudocode

```c
__int64 __fastcall AddExistingEntryToXmlWriter(__int64 a1, __int64 a2)
{
  struct TenantGatewayMap *Instance; // rsi
  _QWORD *v5; // rsi
  _QWORD *i; // rdi
  _QWORD *v7; // rbx
  int v8; // r14d
  _QWORD *j; // rbx
  _QWORD *v10; // rdx
  const wchar_t *v11; // rdx
  unsigned int v12; // ebx
  __int64 v14[5]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v15[8]; // [rsp+58h] [rbp-A8h] BYREF
  int v16; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v17[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v14[4] = a2;
  Instance = TenantGatewayMap::GetInstance();
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  v5 = (_QWORD *)*((_QWORD *)Instance + 2);
  for ( i = (_QWORD *)*v5; ; i = (_QWORD *)*i )
  {
    if ( i == v5 )
    {
      v12 = 0;
      goto LABEL_32;
    }
    v7 = i + 2;
    std::vector<std::wstring>::vector<std::wstring>(v14, i + 7);
    if ( *(_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::find(
                      a2,
                      v15,
                      i + 2) != *(_QWORD *)(a2 + 8) )
      goto LABEL_18;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)a1 + 216LL))(
           a1,
           0,
           L"Tenant",
           0);
    if ( v8 )
      break;
    if ( i[5] >= 8u )
      v7 = (_QWORD *)*v7;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a1 + 224LL))(a1, v7);
    if ( v8 )
    {
LABEL_21:
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_27;
      v11 = L"AddExistingEntryToXmlWriter: WriteString of IXmlWriter object failed with error %d";
      goto LABEL_25;
    }
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 136LL))(a1);
    if ( v8 )
    {
LABEL_19:
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_27;
      v11 = L"AddExistingEntryToXmlWriter: WriteFullEndElement of IXmlWriter object failed with error %d";
      goto LABEL_25;
    }
    for ( j = (_QWORD *)v14[0]; j != (_QWORD *)v14[1]; j += 5 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)a1 + 216LL))(
             a1,
             0,
             L"Gateway",
             0);
      if ( v8 )
        goto LABEL_23;
      if ( j[3] < 8u )
        v10 = j;
      else
        v10 = (_QWORD *)*j;
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a1 + 224LL))(a1, v10);
      if ( v8 )
        goto LABEL_21;
      v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 136LL))(a1);
      if ( v8 )
        goto LABEL_19;
    }
LABEL_18:
    std::vector<std::wstring>::_Tidy((__int64)v14);
  }
LABEL_23:
  if ( (byte_18002D803 & 8) == 0 )
    goto LABEL_27;
  v11 = L"AddExistingEntryToXmlWriter: WriteStartElement of IXmlWriter object failed with error %d";
LABEL_25:
  LOWORD(v16) = 0;
  FormatRRASErrorString(&v16, v11, (unsigned int)v8);
  if ( (byte_18002D803 & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v16);
LABEL_27:
  std::vector<std::wstring>::_Tidy((__int64)v14);
  v12 = 0;
  if ( v8 < 0 )
  {
    if ( (v8 & 0x1FFF0000) == 0x70000 )
      v12 = (unsigned __int16)v8;
    else
      v12 = v8;
  }
LABEL_32:
  std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(a2);
  return v12;
}

```

## disassembly

```asm
0x18000ff74  mov     [rsp-8+arg_10], rbx
0x18000ff79  mov     [rsp-8+arg_18], rsi
0x18000ff7e  push    rbp
0x18000ff7f  push    rdi
0x18000ff80  push    r13
0x18000ff82  push    r14
0x18000ff84  push    r15
0x18000ff86  lea     rbp, [rsp-770h]
0x18000ff8e  sub     rsp, 870h
0x18000ff95  mov     rax, cs:__security_cookie
0x18000ff9c  xor     rax, rsp
0x18000ff9f  mov     [rbp+790h+var_30], rax
0x18000ffa6  mov     r13, rdx
0x18000ffa9  mov     r15, rcx
0x18000ffac  mov     [rsp+890h+var_840], rdx
0x18000ffb1  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x18000ffb6  mov     rsi, rax
0x18000ffb9  xor     edx, edx; Val
0x18000ffbb  mov     [rsp+890h+var_830], edx
0x18000ffbf  mov     r8d, 7FCh; Size
0x18000ffc5  lea     rcx, [rsp+890h+var_82C]; void *
0x18000ffca  call    memset_0
0x18000ffcf  mov     rsi, [rsi+10h]
0x18000ffd3  mov     rdi, [rsi]
0x18000ffd6  cmp     rdi, rsi
0x18000ffd9  jz      loc_18001019E
0x18000ffdf  lea     rbx, [rdi+10h]
0x18000ffe3  lea     rdx, [rbx+28h]
0x18000ffe7  lea     rcx, [rsp+890h+var_860]
0x18000ffec  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x18000fff1  nop
0x18000fff2  mov     r8, rbx
0x18000fff5  lea     rdx, [rsp+890h+var_838]
0x18000fffa  mov     rcx, r13
0x18000fffd  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180010002  mov     rcx, [r13+8]
0x180010006  cmp     [rax], rcx
0x180010009  jnz     loc_1800100F7
0x18001000f  mov     rax, [r15]
0x180010012  xor     r9d, r9d
0x180010015  lea     r8, aTenant; "Tenant"
0x18001001c  xor     edx, edx
0x18001001e  mov     rcx, r15
0x180010021  mov     rax, [rax+0D8h]
0x180010028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001002d  mov     r14d, eax
0x180010030  test    eax, eax
0x180010032  jnz     loc_18001012D
0x180010038  mov     rax, [r15]
0x18001003b  cmp     qword ptr [rbx+18h], 8
0x180010040  jb      short loc_180010045
0x180010042  mov     rbx, [rbx]
0x180010045  mov     rdx, rbx
0x180010048  mov     rcx, r15
0x18001004b  mov     rax, [rax+0E0h]
0x180010052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010057  mov     r14d, eax
0x18001005a  test    eax, eax
0x18001005c  jnz     loc_18001011B
0x180010062  mov     rax, [r15]
0x180010065  mov     rcx, r15
0x180010068  mov     rax, [rax+88h]
0x18001006f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010074  mov     r14d, eax
0x180010077  test    eax, eax
0x180010079  jnz     loc_180010109
0x18001007f  mov     rbx, [rsp+890h+var_860]
0x180010084  cmp     rbx, [rsp+890h+var_858]
0x180010089  jz      short loc_1800100F7
0x18001008b  mov     rax, [r15]
0x18001008e  xor     r9d, r9d
0x180010091  lea     r8, aGateway; "Gateway"
0x180010098  xor     edx, edx
0x18001009a  mov     rcx, r15
0x18001009d  mov     rax, [rax+0D8h]
0x1800100a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100a9  mov     r14d, eax
0x1800100ac  test    eax, eax
0x1800100ae  jnz     short loc_18001012D
0x1800100b0  mov     rax, [r15]
0x1800100b3  cmp     qword ptr [rbx+18h], 8
0x1800100b8  jb      short loc_1800100BF
0x1800100ba  mov     rdx, [rbx]
0x1800100bd  jmp     short loc_1800100C2
0x1800100bf  mov     rdx, rbx
0x1800100c2  mov     rcx, r15
0x1800100c5  mov     rax, [rax+0E0h]
0x1800100cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100d1  mov     r14d, eax
0x1800100d4  test    eax, eax
0x1800100d6  jnz     short loc_18001011B
0x1800100d8  mov     rax, [r15]
0x1800100db  mov     rcx, r15
0x1800100de  mov     rax, [rax+88h]
0x1800100e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100ea  mov     r14d, eax
0x1800100ed  test    eax, eax
0x1800100ef  jnz     short loc_180010109
0x1800100f1  add     rbx, 28h ; '('
0x1800100f5  jmp     short loc_180010084
0x1800100f7  lea     rcx, [rsp+890h+var_860]
0x1800100fc  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180010101  mov     rdi, [rdi]
0x180010104  jmp     loc_18000FFD6
0x180010109  test    cs:byte_18002D803, 8
0x180010110  jz      short loc_180010173
0x180010112  lea     rdx, aAddexistingent; "AddExistingEntryToXmlWriter: WriteFullE"...
0x180010119  jmp     short loc_18001013D
0x18001011b  test    cs:byte_18002D803, 8
0x180010122  jz      short loc_180010173
0x180010124  lea     rdx, aAddexistingent_1; "AddExistingEntryToXmlWriter: WriteStrin"...
0x18001012b  jmp     short loc_18001013D
0x18001012d  test    cs:byte_18002D803, 8
0x180010134  jz      short loc_180010173
0x180010136  lea     rdx, aAddexistingent_0; "AddExistingEntryToXmlWriter: WriteStart"...
0x18001013d  xor     eax, eax
0x18001013f  mov     word ptr [rsp+890h+var_830], ax
0x180010144  mov     r8d, r14d
0x180010147  lea     rcx, [rsp+890h+var_830]
0x18001014c  call    FormatRRASErrorString
0x180010151  test    cs:byte_18002D803, 8
0x180010158  jz      short loc_180010173
0x18001015a  lea     r8, [rsp+890h+var_830]
0x18001015f  lea     rdx, RasSSTPSvcTraceError
0x180010166  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001016d  call    McTemplateU0z_EventWriteTransfer
0x180010172  nop
0x180010173  lea     rcx, [rsp+890h+var_860]
0x180010178  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001017d  xor     ebx, ebx
0x18001017f  test    r14d, r14d
0x180010182  jns     short loc_1800101A0
0x180010184  mov     eax, r14d
0x180010187  and     eax, 1FFF0000h
0x18001018c  cmp     eax, 70000h
0x180010191  jnz     short loc_180010199
0x180010193  movzx   ebx, r14w
0x180010197  jmp     short loc_1800101A0
0x180010199  mov     ebx, r14d
0x18001019c  jmp     short loc_1800101A0
0x18001019e  xor     ebx, ebx
0x1800101a0  mov     rcx, r13
0x1800101a3  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>(void)
0x1800101a8  mov     eax, ebx
0x1800101aa  mov     rcx, [rbp+790h+var_30]
0x1800101b1  xor     rcx, rsp; StackCookie
0x1800101b4  call    __security_check_cookie
0x1800101b9  lea     r11, [rsp+890h+var_20]
0x1800101c1  mov     rbx, [r11+40h]
0x1800101c5  mov     rsi, [r11+48h]
0x1800101c9  mov     rsp, r11
0x1800101cc  pop     r15
0x1800101ce  pop     r14
0x1800101d0  pop     r13
0x1800101d2  pop     rdi
0x1800101d3  pop     rbp
0x1800101d4  retn
```
