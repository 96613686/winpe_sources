# SrSettings::CSrSettings::GetRegValue(HKEY__ *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x1800485bc`
- end: `0x180048836`
- name: `?GetRegValue@CSrSettings@SrSettings@@AEAAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `634`
- prototype: `__int64 __fastcall(__int64, HKEY, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800480a8`

## callees

- `0x18000c6f0`
- `0x180046758`
- `0x1800485bc`
- `0x18004a650`
- `0x18004c0e8`
- `0x18004c6a0`
- `0x18004c6c8`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x18004864a`
- `ADVAPI32!RegGetValueW` at `0x1800486e0`
- `ADVAPI32!RegGetValueW` at `0x1800487ba`
- `ADVAPI32!RegGetValueW` at `0x18004864a`
- `ADVAPI32!RegGetValueW` at `0x1800486e0`
- `ADVAPI32!RegGetValueW` at `0x1800487ba`

## string_xrefs

- `0x1800487d3`: `Failed to get string registry value %s. Error: 0x%08x`
- `0x1800487ee`: `Failed to assign string registry value to string. Error: 0x%08x`
- `0x180048699`: `Invalid registry value size %d for type REG_DWORD`
- `0x1800486f6`: `Failed to get DWORD registry value %s. Error: 0x%08x`
- `0x18004877c`: `Failed to assign DWORD registry value to string. Error: 0x%08x`
- `0x180048686`: `Unsupported registry value type %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SrSettings::CSrSettings::GetRegValue(__int64 a1, HKEY a2, const WCHAR *a3, __int64 a4)
{
  LSTATUS ValueW; // eax
  signed int v9; // ebx
  const wchar_t *v10; // r8
  LSTATUS v11; // eax
  const wchar_t *v12; // r8
  int v13; // eax
  __int64 v14; // r8
  const wchar_t *v15; // r8
  PVOID v16; // r14
  LSTATUS v17; // eax
  LPDWORD pdwType; // [rsp+20h] [rbp-99h]
  DWORD pcbData; // [rsp+40h] [rbp-79h] BYREF
  DWORD v21; // [rsp+44h] [rbp-75h] BYREF
  unsigned int pvData; // [rsp+48h] [rbp-71h] BYREF
  PVOID v23[3]; // [rsp+50h] [rbp-69h] BYREF
  int v24; // [rsp+68h] [rbp-51h]
  __int64 v25; // [rsp+70h] [rbp-49h]
  unsigned __int16 v26[32]; // [rsp+80h] [rbp-39h] BYREF

  v25 = -2;
  v21 = 0;
  pcbData = 0;
  pvData = 0;
  memset(v23, 0, sizeof(v23));
  v24 = 0;
  memset_0(v26, 0, sizeof(v26));
  ValueW = RegGetValueW(a2, 0, a3, 0x1000FFFFu, &v21, 0, &pcbData);
  v9 = ValueW;
  if ( ValueW > 0 )
    v9 = (unsigned __int16)ValueW | 0x80070000;
  if ( (unsigned int)(v9 + 2147024894) > 1 )
  {
    if ( v21 == 1 )
    {
      ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::SetCount(v23, pcbData);
      v16 = v23[0];
      v17 = RegGetValueW(a2, 0, a3, 0x10000002u, &v21, v23[0], &pcbData);
      v9 = v17;
      if ( v17 > 0 )
        v9 = (unsigned __int16)v17 | 0x80070000;
      if ( v9 < 0 )
      {
        v12 = L"Failed to get string registry value %s. Error: 0x%08x";
        goto LABEL_14;
      }
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                              a4,
                              v16) )
        goto LABEL_28;
      v15 = L"Failed to assign string registry value to string. Error: 0x%08x";
LABEL_27:
      v9 = -2147024888;
      SrSettings::CSrSettings::Trace(a1, 2, v15, 2147942408LL);
      goto LABEL_28;
    }
    if ( v21 != 4 )
    {
      v10 = L"Unsupported registry value type %d";
LABEL_9:
      SrSettings::CSrSettings::Trace(a1, 2, v10);
      v9 = -2147024809;
      goto LABEL_28;
    }
    if ( pcbData != 4 )
    {
      v10 = L"Invalid registry value size %d for type REG_DWORD";
      goto LABEL_9;
    }
    v11 = RegGetValueW(a2, 0, a3, 0x10000010u, &v21, &pvData, &pcbData);
    v9 = v11;
    if ( v11 > 0 )
      v9 = (unsigned __int16)v11 | 0x80070000;
    if ( v9 < 0 )
    {
      v12 = L"Failed to get DWORD registry value %s. Error: 0x%08x";
LABEL_14:
      LODWORD(pdwType) = v9;
      SrSettings::CSrSettings::Trace(a1, 2, v12, a3, pdwType);
      goto LABEL_28;
    }
    v13 = StringCchPrintfW(v26, 0x20u, L"%u", pvData);
    v9 = v13;
    if ( v13 < 0 )
    {
      LODWORD(pdwType) = v13;
      SrSettings::CSrSettings::Trace(a1, 2, L"Failed to convert DWORD [%u] to string. Error: 0x%08x", pvData, pdwType);
      goto LABEL_28;
    }
    v14 = -1;
    do
      ++v14;
    while ( v26[v14] );
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             a4,
                             v26,
                             v14) )
    {
      v15 = L"Failed to assign DWORD registry value to string. Error: 0x%08x";
      goto LABEL_27;
    }
  }
LABEL_28:
  ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>(v23);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800485bc  push    rbp
0x1800485be  push    rbx
0x1800485bf  push    rsi
0x1800485c0  push    rdi
0x1800485c1  push    r12
0x1800485c3  push    r13
0x1800485c5  push    r14
0x1800485c7  push    r15
0x1800485c9  lea     rbp, [rsp-1Fh]
0x1800485ce  sub     rsp, 0D8h
0x1800485d5  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x1800485dd  mov     rax, cs:__security_cookie
0x1800485e4  xor     rax, rsp
0x1800485e7  mov     [rbp+57h+var_50], rax
0x1800485eb  mov     r12, r9
0x1800485ee  mov     rsi, r8
0x1800485f1  mov     r15, rdx
0x1800485f4  mov     rdi, rcx
0x1800485f7  xor     r13d, r13d
0x1800485fa  mov     [rbp+57h+var_CC], r13d
0x1800485fe  mov     [rbp+57h+var_D0], r13d
0x180048602  mov     [rbp+57h+var_C8], r13d
0x180048606  mov     [rbp+57h+var_C0], r13
0x18004860a  mov     [rbp+57h+var_B8], r13
0x18004860e  mov     [rbp+57h+var_B0], r13
0x180048612  mov     [rbp+57h+var_A8], r13d
0x180048616  xor     edx, edx; Val
0x180048618  lea     r8d, [r13+40h]; Size
0x18004861c  lea     rcx, [rbp+57h+var_90]; void *
0x180048620  call    memset_0
0x180048625  lea     rax, [rbp+57h+var_D0]
0x180048629  mov     [rsp+110h+pcbData], rax; pcbData
0x18004862e  mov     [rsp+110h+pvData], r13; pvData
0x180048633  lea     rax, [rbp+57h+var_CC]
0x180048637  mov     [rsp+110h+pdwType], rax; pdwType
0x18004863c  mov     r9d, 1000FFFFh; dwFlags
0x180048642  mov     r8, rsi; lpValue
0x180048645  xor     edx, edx; lpSubKey
0x180048647  mov     rcx, r15; hkey
0x18004864a  call    cs:__imp_RegGetValueW
0x180048650  mov     ebx, eax
0x180048652  mov     r14d, 80070000h
0x180048658  test    eax, eax
0x18004865a  jle     short loc_180048662
0x18004865c  movzx   ebx, ax
0x18004865f  or      ebx, r14d
0x180048662  lea     eax, [rbx+7FF8FFFEh]
0x180048668  cmp     eax, 1
0x18004866b  jbe     loc_18004880B
0x180048671  mov     r9d, [rbp+57h+var_CC]
0x180048675  mov     eax, r9d
0x180048678  sub     eax, 1
0x18004867b  jz      loc_180048785
0x180048681  cmp     eax, 3
0x180048684  jz      short loc_18004868F
0x180048686  lea     r8, aUnsupportedReg; "Unsupported registry value type %d"
0x18004868d  jmp     short loc_1800486A0
0x18004868f  mov     r9d, [rbp+57h+var_D0]
0x180048693  cmp     r9d, 4
0x180048697  jz      short loc_1800486B7
0x180048699  lea     r8, aInvalidRegistr_0; "Invalid registry value size %d for type"...
0x1800486a0  mov     edx, 2
0x1800486a5  mov     rcx, rdi
0x1800486a8  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800486ad  mov     ebx, 80070057h
0x1800486b2  jmp     loc_18004880B
0x1800486b7  lea     rax, [rbp+57h+var_D0]
0x1800486bb  mov     [rsp+110h+pcbData], rax; pcbData
0x1800486c0  lea     rax, [rbp+57h+var_C8]
0x1800486c4  mov     [rsp+110h+pvData], rax; pvData
0x1800486c9  lea     rax, [rbp+57h+var_CC]
0x1800486cd  mov     [rsp+110h+pdwType], rax; pdwType
0x1800486d2  mov     r9d, 10000010h; dwFlags
0x1800486d8  mov     r8, rsi; lpValue
0x1800486db  xor     edx, edx; lpSubKey
0x1800486dd  mov     rcx, r15; hkey
0x1800486e0  call    cs:__imp_RegGetValueW
0x1800486e6  mov     ebx, eax
0x1800486e8  test    eax, eax
0x1800486ea  jle     short loc_1800486F2
0x1800486ec  movzx   ebx, ax
0x1800486ef  or      ebx, r14d
0x1800486f2  test    ebx, ebx
0x1800486f4  jns     short loc_180048716
0x1800486f6  lea     r8, aFailedToGetDwo; "Failed to get DWORD registry value %s. "...
0x1800486fd  mov     r9, rsi
0x180048700  mov     dword ptr [rsp+110h+pdwType], ebx
0x180048704  mov     edx, 2
0x180048709  mov     rcx, rdi
0x18004870c  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180048711  jmp     loc_18004880B
0x180048716  mov     r9d, [rbp+57h+var_C8]
0x18004871a  lea     r8, aU; "%u"
0x180048721  mov     edx, 20h ; ' '; unsigned __int64
0x180048726  lea     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x18004872a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004872f  mov     ebx, eax
0x180048731  test    eax, eax
0x180048733  jns     short loc_180048756
0x180048735  mov     dword ptr [rsp+110h+pdwType], eax
0x180048739  mov     r9d, [rbp+57h+var_C8]
0x18004873d  lea     r8, aFailedToConver_3; "Failed to convert DWORD [%u] to string."...
0x180048744  mov     edx, 2
0x180048749  mov     rcx, rdi
0x18004874c  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180048751  jmp     loc_18004880B
0x180048756  lea     rax, [rbp+57h+var_90]
0x18004875a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004875e  inc     r8
0x180048761  cmp     [rax+r8*2], r13w
0x180048766  jnz     short loc_18004875E
0x180048768  lea     rdx, [rbp+57h+var_90]
0x18004876c  mov     rcx, r12
0x18004876f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180048774  test    al, al
0x180048776  jnz     loc_18004880B
0x18004877c  lea     r8, aFailedToAssign_10; "Failed to assign DWORD registry value t"...
0x180048783  jmp     short loc_1800487F5
0x180048785  mov     edx, [rbp+57h+var_D0]
0x180048788  lea     rcx, [rbp+57h+var_C0]
0x18004878c  call    ?SetCount@?$CAtlArray@EV?$CElementTraits@E@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<uchar,ATL::CElementTraits<uchar>>::SetCount(unsigned __int64,int)
0x180048791  lea     rax, [rbp+57h+var_D0]
0x180048795  mov     [rsp+110h+pcbData], rax; pcbData
0x18004879a  mov     r14, [rbp+57h+var_C0]
0x18004879e  mov     [rsp+110h+pvData], r14; pvData
0x1800487a3  lea     rax, [rbp+57h+var_CC]
0x1800487a7  mov     [rsp+110h+pdwType], rax; pdwType
0x1800487ac  mov     r9d, 10000002h; dwFlags
0x1800487b2  mov     r8, rsi; lpValue
0x1800487b5  xor     edx, edx; lpSubKey
0x1800487b7  mov     rcx, r15; hkey
0x1800487ba  call    cs:__imp_RegGetValueW
0x1800487c0  mov     ebx, eax
0x1800487c2  test    eax, eax
0x1800487c4  jle     short loc_1800487CF
0x1800487c6  movzx   ebx, ax
0x1800487c9  or      ebx, 80070000h
0x1800487cf  test    ebx, ebx
0x1800487d1  jns     short loc_1800487DF
0x1800487d3  lea     r8, aFailedToGetStr_0; "Failed to get string registry value %s."...
0x1800487da  jmp     loc_1800486FD
0x1800487df  mov     rdx, r14
0x1800487e2  mov     rcx, r12
0x1800487e5  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800487ea  test    al, al
0x1800487ec  jnz     short loc_18004880B
0x1800487ee  lea     r8, aFailedToAssign_8; "Failed to assign string registry value "...
0x1800487f5  mov     ebx, 80070008h
0x1800487fa  mov     r9d, ebx
0x1800487fd  mov     edx, 2
0x180048802  mov     rcx, rdi
0x180048805  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004880a  nop
0x18004880b  lea     rcx, [rbp+57h+var_C0]
0x18004880f  call    ??1?$CAtlArray@EV?$CElementTraits@E@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<uchar,ATL::CElementTraits<uchar>>::~CAtlArray<uchar,ATL::CElementTraits<uchar>>(void)
0x180048814  mov     eax, ebx
0x180048816  mov     rcx, [rbp+57h+var_50]
0x18004881a  xor     rcx, rsp; StackCookie
0x18004881d  call    __security_check_cookie
0x180048822  add     rsp, 0D8h
0x180048829  pop     r15
0x18004882b  pop     r14
0x18004882d  pop     r13
0x18004882f  pop     r12
0x180048831  pop     rdi
0x180048832  pop     rsi
0x180048833  pop     rbx
0x180048834  pop     rbp
0x180048835  retn
```
