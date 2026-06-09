# WindowsMidiServicesNamingLib::MidiEndpointNameTable::PopulateAllEntriesForNativeUmpDevice(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal,std::allocator<WindowsMidiServicesInternal::GroupTerminalBlockInternal>> &)

- ea: `0x18002c91c`
- end: `0x18002caaf`
- name: `?PopulateAllEntriesForNativeUmpDevice@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@V?$allocator@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@@std@@@4@@Z`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18001d454`

## callees

- `0x180004180`
- `0x18000b740`
- `0x18000e178`
- `0x18000f0a4`
- `0x18001b624`
- `0x18002c91c`
- `0x18002cab8`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesNamingLib::MidiEndpointNameTable::PopulateAllEntriesForNativeUmpDevice(
        __int64 a1,
        wchar_t *a2,
        _QWORD *a3)
{
  char v5; // si
  char v6; // bp
  _BYTE *v7; // r14
  _BYTE *i; // rbx
  unsigned int v9; // edi
  int v10; // eax
  int v11; // eax
  int v13; // [rsp+20h] [rbp-A8h]
  int v14; // [rsp+20h] [rbp-A8h]
  _OWORD v15[2]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v16[32]; // [rsp+60h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v5 = 0;
  v6 = 0;
  v7 = (_BYTE *)a3[1];
  for ( i = (_BYTE *)*a3; i != v7; i += 48 )
  {
    v9 = (unsigned __int8)i[2];
    if ( v9 < v9 + (unsigned __int8)i[3] )
    {
      do
      {
        memset(v15, 0, sizeof(v15));
        std::wstring::_Construct<1,unsigned short const *>(v15, &S2);
        std::wstring::wstring(v16, i + 16);
        if ( (i[1] & 0xFD) == 0 )
        {
          v10 = WindowsMidiServicesNamingLib::MidiEndpointNameTable::PopulateEntryForNativeUmpDevice(
                  a1,
                  v9,
                  0,
                  (__int64)v15,
                  a2,
                  (__int64)a2,
                  (__int64)(i + 16),
                  v5);
          if ( v10 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2E6,
              (unsigned int)"avcore\\midi2\\libs\\midiendpointnaminglib\\midiendpointnametable.cpp",
              (const char *)(unsigned int)v10,
              v13);
          ++v5;
        }
        if ( i[1] <= 1u )
        {
          v11 = WindowsMidiServicesNamingLib::MidiEndpointNameTable::PopulateEntryForNativeUmpDevice(
                  a1,
                  v9,
                  1,
                  (__int64)v15,
                  a2,
                  (__int64)a2,
                  (__int64)(i + 16),
                  v6);
          if ( v11 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2F5,
              (unsigned int)"avcore\\midi2\\libs\\midiendpointnaminglib\\midiendpointnametable.cpp",
              (const char *)(unsigned int)v11,
              v14);
          ++v6;
        }
        std::wstring::~wstring(v16);
        std::wstring::~wstring(v15);
        LOBYTE(v9) = v9 + 1;
      }
      while ( (unsigned __int8)v9 < (unsigned __int8)i[2] + (unsigned int)(unsigned __int8)i[3] );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002c91c  mov     [rsp+arg_18], rbx
0x18002c921  push    rbp
0x18002c922  push    rsi
0x18002c923  push    rdi
0x18002c924  push    r12
0x18002c926  push    r13
0x18002c928  push    r14
0x18002c92a  push    r15
0x18002c92c  sub     rsp, 90h
0x18002c933  mov     rax, cs:__security_cookie
0x18002c93a  xor     rax, rsp
0x18002c93d  mov     [rsp+0C8h+var_48], rax
0x18002c945  mov     r15, rdx
0x18002c948  mov     r13, rcx
0x18002c94b  xor     sil, sil
0x18002c94e  xor     bpl, bpl
0x18002c951  mov     r14, [r8+8]
0x18002c955  mov     rbx, [r8]
0x18002c958  jmp     loc_18002CA79
0x18002c95d  movzx   edi, byte ptr [rbx+2]
0x18002c961  movzx   eax, byte ptr [rbx+3]
0x18002c965  add     eax, edi
0x18002c967  cmp     edi, eax
0x18002c969  jnb     loc_18002CA75
0x18002c96f  lea     r12, [rbx+10h]
0x18002c973  xorps   xmm0, xmm0
0x18002c976  movups  [rsp+0C8h+var_88], xmm0
0x18002c97b  xorps   xmm1, xmm1
0x18002c97e  movdqu  [rsp+0C8h+var_78], xmm1
0x18002c984  xor     r8d, r8d
0x18002c987  lea     rdx, S2
0x18002c98e  lea     rcx, [rsp+0C8h+var_88]
0x18002c993  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002c998  mov     rdx, r12
0x18002c99b  lea     rcx, [rsp+0C8h+var_68]
0x18002c9a0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002c9a5  test    byte ptr [rbx+1], 0FDh
0x18002c9a9  jnz     short loc_18002C9F5
0x18002c9ab  mov     [rsp+0C8h+var_90], sil
0x18002c9b0  mov     [rsp+0C8h+var_98], r12
0x18002c9b5  mov     [rsp+0C8h+var_A0], r15
0x18002c9ba  mov     qword ptr [rsp+0C8h+var_A8], r15; int
0x18002c9bf  lea     r9, [rsp+0C8h+var_88]
0x18002c9c4  xor     r8d, r8d
0x18002c9c7  mov     dl, dil
0x18002c9ca  mov     rcx, r13
0x18002c9cd  call    ?PopulateEntryForNativeUmpDevice@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAAJEW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111E@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::PopulateEntryForNativeUmpDevice(uchar,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,uchar)
0x18002c9d2  test    eax, eax
0x18002c9d4  jns     short loc_18002C9F2
0x18002c9d6  mov     rcx, [rsp+0C8h]; this
0x18002c9de  mov     r9d, eax; char *
0x18002c9e1  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiendpointnaming"...
0x18002c9e8  mov     edx, 2E6h; void *
0x18002c9ed  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c9f2  inc     sil
0x18002c9f5  cmp     byte ptr [rbx+1], 1
0x18002c9f9  ja      short loc_18002CA48
0x18002c9fb  mov     [rsp+0C8h+var_90], bpl
0x18002ca00  mov     [rsp+0C8h+var_98], r12
0x18002ca05  mov     [rsp+0C8h+var_A0], r15
0x18002ca0a  mov     qword ptr [rsp+0C8h+var_A8], r15; int
0x18002ca0f  lea     r9, [rsp+0C8h+var_88]
0x18002ca14  mov     r8d, 1
0x18002ca1a  mov     dl, dil
0x18002ca1d  mov     rcx, r13
0x18002ca20  call    ?PopulateEntryForNativeUmpDevice@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAAJEW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111E@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::PopulateEntryForNativeUmpDevice(uchar,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,uchar)
0x18002ca25  test    eax, eax
0x18002ca27  jns     short loc_18002CA45
0x18002ca29  mov     rcx, [rsp+0C8h]; this
0x18002ca31  mov     r9d, eax; char *
0x18002ca34  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiendpointnaming"...
0x18002ca3b  mov     edx, 2F5h; void *
0x18002ca40  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ca45  inc     bpl
0x18002ca48  lea     rcx, [rsp+0C8h+var_68]; void *
0x18002ca4d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ca52  lea     rcx, [rsp+0C8h+var_88]; void *
0x18002ca57  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ca5c  inc     dil
0x18002ca5f  movzx   ecx, byte ptr [rbx+3]
0x18002ca63  movzx   eax, byte ptr [rbx+2]
0x18002ca67  add     ecx, eax
0x18002ca69  movzx   eax, dil
0x18002ca6d  cmp     eax, ecx
0x18002ca6f  jb      loc_18002C973
0x18002ca75  add     rbx, 30h ; '0'
0x18002ca79  cmp     rbx, r14
0x18002ca7c  jnz     loc_18002C95D
0x18002ca82  xor     eax, eax
0x18002ca84  mov     rcx, [rsp+0C8h+var_48]
0x18002ca8c  xor     rcx, rsp; StackCookie
0x18002ca8f  call    __security_check_cookie
0x18002ca94  mov     rbx, [rsp+0C8h+arg_18]
0x18002ca9c  add     rsp, 90h
0x18002caa3  pop     r15
0x18002caa5  pop     r14
0x18002caa7  pop     r13
0x18002caa9  pop     r12
0x18002caab  pop     rdi
0x18002caac  pop     rsi
0x18002caad  pop     rbp
0x18002caae  retn
```
