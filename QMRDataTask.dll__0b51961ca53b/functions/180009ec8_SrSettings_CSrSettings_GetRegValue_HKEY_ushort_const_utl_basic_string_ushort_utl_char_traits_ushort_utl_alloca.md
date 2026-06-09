# SrSettings::CSrSettings::GetRegValue(HKEY__ *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180009ec8`
- end: `0x18000a1b9`
- name: `?GetRegValue@CSrSettings@SrSettings@@AEAAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `753`
- prototype: `__int64 __fastcall(__int64, HKEY, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009494`

## callees

- `0x180006bf0`
- `0x180009ec8`
- `0x18000afa0`
- `0x1800105f8`
- `0x180010a0c`
- `0x180011c80`
- `0x1800142d2`
- `0x180014310`

## import_xrefs

- `msvcrt!free` at `0x18000a148`
- `msvcrt!free` at `0x18000a148`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180009f51`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180009ff9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a10b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180009f51`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180009ff9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a10b`

## string_xrefs

- `0x18000a12b`: `Failed to get string registry value %s. Error: 0x%08x`
- `0x18000a181`: `Failed to assign string registry value to string. Error: 0x%08x`
- `0x180009fb2`: `Invalid registry value size %d for type REG_DWORD`
- `0x18000a019`: `Failed to get DWORD registry value %s. Error: 0x%08x`
- `0x18000a09d`: `Failed to assign DWORD registry value to string. Error: 0x%08x`
- `0x180009f8a`: `Unsupported registry value type %d`

## pseudocode

```c
__int64 __fastcall SrSettings::CSrSettings::GetRegValue(__int64 a1, HKEY a2, const WCHAR *a3, __int64 a4)
{
  void *v8; // rdi
  LSTATUS ValueW; // eax
  unsigned int v10; // ecx
  signed int v11; // ebx
  LSTATUS v12; // eax
  int v13; // eax
  unsigned __int64 v14; // r8
  __int64 v15; // rbx
  LSTATUS v16; // eax
  unsigned __int64 v18; // r8
  LPDWORD pdwType; // [rsp+20h] [rbp-89h]
  LPDWORD pdwTypea; // [rsp+20h] [rbp-89h]
  DWORD pcbData; // [rsp+40h] [rbp-69h] BYREF
  DWORD v22; // [rsp+44h] [rbp-65h] BYREF
  unsigned int pvData; // [rsp+48h] [rbp-61h] BYREF
  void *v24; // [rsp+50h] [rbp-59h] BYREF
  __int64 v25; // [rsp+58h] [rbp-51h]
  __int64 v26; // [rsp+60h] [rbp-49h]
  int v27; // [rsp+68h] [rbp-41h]
  unsigned __int16 v28[32]; // [rsp+70h] [rbp-39h] BYREF

  v22 = 0;
  pcbData = 0;
  pvData = 0;
  v8 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  ValueW = RegGetValueW(a2, 0, a3, 0x1000FFFFu, &v22, 0, &pcbData);
  v10 = ValueW;
  if ( ValueW > 0 )
    v10 = (unsigned __int16)ValueW | 0x80070000;
  if ( v10 + 2147024894 > 1 )
  {
    if ( v22 == 1 )
    {
      v15 = pcbData;
      if ( pcbData )
      {
        if ( (unsigned __int8)ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::GrowBuffer(
                                &v24,
                                pcbData) )
        {
          ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::CallConstructors();
          v25 = v15;
        }
        v8 = v24;
      }
      else
      {
        v25 = 0;
        v26 = 0;
      }
      v16 = RegGetValueW(a2, 0, a3, 0x10000002u, &v22, v8, &pcbData);
      v11 = v16;
      if ( v16 > 0 )
        v11 = (unsigned __int16)v16 | 0x80070000;
      if ( v11 >= 0 )
      {
        if ( v8 )
        {
          v18 = -1;
          do
            ++v18;
          while ( *((_WORD *)v8 + v18) );
        }
        else
        {
          v18 = 0;
        }
        if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                a4,
                v8,
                v18) )
        {
          v11 = -2147024888;
          SrSettings::CSrSettings::Trace(
            a1,
            2,
            L"Failed to assign string registry value to string. Error: 0x%08x",
            2147942408LL);
        }
      }
      else
      {
        LODWORD(pdwTypea) = v11;
        SrSettings::CSrSettings::Trace(a1, 2, L"Failed to get string registry value %s. Error: 0x%08x", a3, pdwTypea);
      }
      goto LABEL_28;
    }
    if ( v22 != 4 )
    {
      SrSettings::CSrSettings::Trace(a1, 2, L"Unsupported registry value type %d");
      v11 = -2147024809;
LABEL_28:
      if ( v8 )
        free(v8);
      return (unsigned int)v11;
    }
    if ( pcbData == 4 )
    {
      v12 = RegGetValueW(a2, 0, a3, 0x10000010u, &v22, &pvData, &pcbData);
      v11 = v12;
      if ( v12 > 0 )
        v11 = (unsigned __int16)v12 | 0x80070000;
      if ( v11 >= 0 )
      {
        v13 = StringCchPrintfW(v28, 0x20u, L"%u", pvData);
        v11 = v13;
        if ( v13 >= 0 )
        {
          v14 = -1;
          do
            ++v14;
          while ( v28[v14] );
          if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                 a4,
                 v28,
                 v14) )
          {
            goto LABEL_28;
          }
          v11 = -2147024888;
          SrSettings::CSrSettings::Trace(
            a1,
            2,
            L"Failed to assign DWORD registry value to string. Error: 0x%08x",
            2147942408LL);
        }
        else
        {
          LODWORD(pdwType) = v13;
          SrSettings::CSrSettings::Trace(
            a1,
            2,
            L"Failed to convert DWORD [%u] to string. Error: 0x%08x",
            pvData,
            pdwType);
        }
      }
      else
      {
        LODWORD(pdwType) = v11;
        SrSettings::CSrSettings::Trace(a1, 2, L"Failed to get DWORD registry value %s. Error: 0x%08x", a3, pdwType);
      }
    }
    else
    {
      SrSettings::CSrSettings::Trace(a1, 2, L"Invalid registry value size %d for type REG_DWORD");
      return (unsigned int)-2147024809;
    }
    return (unsigned int)v11;
  }
  return v10;
}

```

## disassembly

```asm
0x180009ec8  push    rbp
0x180009eca  push    rbx
0x180009ecb  push    rsi
0x180009ecc  push    rdi
0x180009ecd  push    r12
0x180009ecf  push    r13
0x180009ed1  push    r14
0x180009ed3  push    r15
0x180009ed5  lea     rbp, [rsp-1Fh]
0x180009eda  sub     rsp, 0C8h
0x180009ee1  mov     rax, cs:__security_cookie
0x180009ee8  xor     rax, rsp
0x180009eeb  mov     [rbp+57h+var_50], rax
0x180009eef  mov     r12, r9
0x180009ef2  mov     r14, r8
0x180009ef5  mov     r15, rdx
0x180009ef8  mov     rsi, rcx
0x180009efb  xor     r13d, r13d
0x180009efe  mov     [rbp+57h+var_BC], r13d
0x180009f02  mov     [rbp+57h+var_C0], r13d
0x180009f06  mov     [rbp+57h+var_B8], r13d
0x180009f0a  mov     edi, r13d
0x180009f0d  mov     [rbp+57h+var_B0], r13
0x180009f11  mov     [rbp+57h+var_A8], r13
0x180009f15  mov     [rbp+57h+var_A0], r13
0x180009f19  mov     [rbp+57h+var_98], r13d
0x180009f1d  xor     edx, edx; Val
0x180009f1f  lea     r8d, [r13+40h]; Size
0x180009f23  lea     rcx, [rbp+57h+var_90]; void *
0x180009f27  call    memset_0
0x180009f2c  lea     rax, [rbp+57h+var_C0]
0x180009f30  mov     [rsp+100h+pcbData], rax; pcbData
0x180009f35  mov     [rsp+100h+pvData], r13; pvData
0x180009f3a  lea     rax, [rbp+57h+var_BC]
0x180009f3e  mov     [rsp+100h+pdwType], rax; pdwType
0x180009f43  mov     r9d, 1000FFFFh; dwFlags
0x180009f49  mov     r8, r14; lpValue
0x180009f4c  xor     edx, edx; lpSubKey
0x180009f4e  mov     rcx, r15; hkey
0x180009f51  call    cs:__imp_RegGetValueW
0x180009f57  mov     ecx, eax
0x180009f59  test    eax, eax
0x180009f5b  jle     short loc_180009F66
0x180009f5d  movzx   ecx, ax
0x180009f60  or      ecx, 80070000h
0x180009f66  lea     eax, [rcx+7FF8FFFEh]
0x180009f6c  cmp     eax, 1
0x180009f6f  jbe     loc_18000A197
0x180009f75  mov     r9d, [rbp+57h+var_BC]
0x180009f79  mov     eax, r9d
0x180009f7c  sub     eax, 1
0x180009f7f  jz      loc_18000A0B7
0x180009f85  cmp     eax, 3
0x180009f88  jz      short loc_180009FA8
0x180009f8a  lea     r8, aUnsupportedReg; "Unsupported registry value type %d"
0x180009f91  mov     edx, 2
0x180009f96  mov     rcx, rsi
0x180009f99  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180009f9e  mov     ebx, 80070057h
0x180009fa3  jmp     loc_18000A140
0x180009fa8  mov     r9d, [rbp+57h+var_C0]
0x180009fac  cmp     r9d, 4
0x180009fb0  jz      short loc_180009FD0
0x180009fb2  lea     r8, aInvalidRegistr_0; "Invalid registry value size %d for type"...
0x180009fb9  mov     edx, 2
0x180009fbe  mov     rcx, rsi
0x180009fc1  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180009fc6  mov     ebx, 80070057h
0x180009fcb  jmp     loc_18000A0B2
0x180009fd0  lea     rax, [rbp+57h+var_C0]
0x180009fd4  mov     [rsp+100h+pcbData], rax; pcbData
0x180009fd9  lea     rax, [rbp+57h+var_B8]
0x180009fdd  mov     [rsp+100h+pvData], rax; pvData
0x180009fe2  lea     rax, [rbp+57h+var_BC]
0x180009fe6  mov     [rsp+100h+pdwType], rax; pdwType
0x180009feb  mov     r9d, 10000010h; dwFlags
0x180009ff1  mov     r8, r14; lpValue
0x180009ff4  xor     edx, edx; lpSubKey
0x180009ff6  mov     rcx, r15; hkey
0x180009ff9  call    cs:__imp_RegGetValueW
0x180009fff  mov     ebx, eax
0x18000a001  test    eax, eax
0x18000a003  jle     short loc_18000A00E
0x18000a005  movzx   ebx, ax
0x18000a008  or      ebx, 80070000h
0x18000a00e  test    ebx, ebx
0x18000a010  jns     short loc_18000A032
0x18000a012  mov     dword ptr [rsp+100h+pdwType], ebx
0x18000a016  mov     r9, r14
0x18000a019  lea     r8, aFailedToGetDwo; "Failed to get DWORD registry value %s. "...
0x18000a020  mov     edx, 2
0x18000a025  mov     rcx, rsi
0x18000a028  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000a02d  jmp     loc_18000A0B2
0x18000a032  mov     r9d, [rbp+57h+var_B8]
0x18000a036  lea     r8, aU_0; "%u"
0x18000a03d  mov     edx, 20h ; ' '; unsigned __int64
0x18000a042  lea     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x18000a046  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a04b  mov     ebx, eax
0x18000a04d  test    eax, eax
0x18000a04f  jns     short loc_18000A06F
0x18000a051  mov     dword ptr [rsp+100h+pdwType], eax
0x18000a055  mov     r9d, [rbp+57h+var_B8]
0x18000a059  lea     r8, aFailedToConver; "Failed to convert DWORD [%u] to string."...
0x18000a060  mov     edx, 2
0x18000a065  mov     rcx, rsi
0x18000a068  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000a06d  jmp     short loc_18000A0B2
0x18000a06f  lea     rax, [rbp+57h+var_90]
0x18000a073  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000a077  inc     r8
0x18000a07a  cmp     [rax+r8*2], r13w
0x18000a07f  jnz     short loc_18000A077
0x18000a081  lea     rdx, [rbp+57h+var_90]
0x18000a085  mov     rcx, r12
0x18000a088  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000a08d  test    al, al
0x18000a08f  jnz     loc_18000A140
0x18000a095  mov     ebx, 80070008h
0x18000a09a  mov     r9d, ebx
0x18000a09d  lea     r8, aFailedToAssign_10; "Failed to assign DWORD registry value t"...
0x18000a0a4  mov     edx, 2
0x18000a0a9  mov     rcx, rsi
0x18000a0ac  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000a0b1  nop
0x18000a0b2  jmp     loc_18000A14E
0x18000a0b7  mov     ebx, [rbp+57h+var_C0]
0x18000a0ba  test    rbx, rbx
0x18000a0bd  jnz     short loc_18000A0C9
0x18000a0bf  mov     [rbp+57h+var_A8], r13
0x18000a0c3  mov     [rbp+57h+var_A0], r13
0x18000a0c7  jmp     short loc_18000A0E6
0x18000a0c9  mov     rdx, rbx
0x18000a0cc  lea     rcx, [rbp+57h+var_B0]
0x18000a0d0  call    ?GrowBuffer@?$CAtlArray@EV?$CElementTraits@E@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<uchar,ATL::CElementTraits<uchar>>::GrowBuffer(unsigned __int64)
0x18000a0d5  test    al, al
0x18000a0d7  jz      short loc_18000A0E2
0x18000a0d9  call    ?CallConstructors@?$CAtlArray@EV?$CElementTraits@E@ATL@@@ATL@@CAXPEAE_K@Z; ATL::CAtlArray<uchar,ATL::CElementTraits<uchar>>::CallConstructors(uchar *,unsigned __int64)
0x18000a0de  mov     [rbp+57h+var_A8], rbx
0x18000a0e2  mov     rdi, [rbp+57h+var_B0]
0x18000a0e6  lea     rax, [rbp+57h+var_C0]
0x18000a0ea  mov     [rsp+100h+pcbData], rax; pcbData
0x18000a0ef  mov     [rsp+100h+pvData], rdi; pvData
0x18000a0f4  lea     rax, [rbp+57h+var_BC]
0x18000a0f8  mov     [rsp+100h+pdwType], rax; pdwType
0x18000a0fd  mov     r9d, 10000002h; dwFlags
0x18000a103  mov     r8, r14; lpValue
0x18000a106  xor     edx, edx; lpSubKey
0x18000a108  mov     rcx, r15; hkey
0x18000a10b  call    cs:__imp_RegGetValueW
0x18000a111  mov     ebx, eax
0x18000a113  test    eax, eax
0x18000a115  jle     short loc_18000A120
0x18000a117  movzx   ebx, ax
0x18000a11a  or      ebx, 80070000h
0x18000a120  test    ebx, ebx
0x18000a122  jns     short loc_18000A152
0x18000a124  mov     dword ptr [rsp+100h+pdwType], ebx
0x18000a128  mov     r9, r14
0x18000a12b  lea     r8, aFailedToGetStr; "Failed to get string registry value %s."...
0x18000a132  mov     edx, 2
0x18000a137  mov     rcx, rsi
0x18000a13a  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000a13f  nop
0x18000a140  test    rdi, rdi
0x18000a143  jz      short loc_18000A14E
0x18000a145  mov     rcx, rdi; Block
0x18000a148  call    cs:__imp_free
0x18000a14e  mov     eax, ebx
0x18000a150  jmp     short loc_18000A199
0x18000a152  test    rdi, rdi
0x18000a155  jz      short loc_18000A167
0x18000a157  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000a15b  inc     r8
0x18000a15e  cmp     [rdi+r8*2], r13w
0x18000a163  jnz     short loc_18000A15B
0x18000a165  jmp     short loc_18000A16A
0x18000a167  mov     r8, r13
0x18000a16a  mov     rdx, rdi
0x18000a16d  mov     rcx, r12
0x18000a170  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000a175  test    al, al
0x18000a177  jnz     short loc_18000A140
0x18000a179  mov     ebx, 80070008h
0x18000a17e  mov     r9d, ebx
0x18000a181  lea     r8, aFailedToAssign_8; "Failed to assign string registry value "...
0x18000a188  mov     edx, 2
0x18000a18d  mov     rcx, rsi
0x18000a190  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000a195  jmp     short loc_18000A140
0x18000a197  mov     eax, ecx
0x18000a199  mov     rcx, [rbp+57h+var_50]
0x18000a19d  xor     rcx, rsp; StackCookie
0x18000a1a0  call    __security_check_cookie
0x18000a1a5  add     rsp, 0C8h
0x18000a1ac  pop     r15
0x18000a1ae  pop     r14
0x18000a1b0  pop     r13
0x18000a1b2  pop     r12
0x18000a1b4  pop     rdi
0x18000a1b5  pop     rsi
0x18000a1b6  pop     rbx
0x18000a1b7  pop     rbp
0x18000a1b8  retn
```
