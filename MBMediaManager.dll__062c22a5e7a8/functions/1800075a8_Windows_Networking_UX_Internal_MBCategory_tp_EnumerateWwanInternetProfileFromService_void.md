# Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanInternetProfileFromService(void)

- ea: `0x1800075a8`
- end: `0x180007991`
- name: `?tp_EnumerateWwanInternetProfileFromService@MBCategory@Internal@UX@Networking@Windows@@AEAAJXZ`
- size: `1001`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::MBCategory *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000ea3c`

## callees

- `0x1800075a8`
- `0x180008c84`
- `0x180009200`
- `0x18000a460`
- `0x18000ad20`
- `0x18002cd20`
- `0x18002d8c8`
- `0x18002f151`
- `0x180055dd0`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800076cb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180007706`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180007740`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180007965`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800076cb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180007706`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180007740`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180007965`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileList` at `0x180007609`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileList` at `0x180007609`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileIstream` at `0x18000768a`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileIstream` at `0x18000768a`

## string_xrefs

- `0x180007818`: `Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanInternetProfileFromService`
- `0x180007839`: `Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanInternetProfileFromService`
- `0x180007934`: `Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanInternetProfileFromService`
- `0x180007953`: `Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanInternetProfileFromService`
- `0x1800076bb`: `Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService`
- `0x1800076f6`: `Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService`
- `0x18000780c`: `_ReadWwanProfileFromService failed. HRESULT=0x%x, _guidInterface=%hs, profileName=%ls`
- `0x18000782d`: `UpdateWwanProfile`
- `0x180007947`: `Complete. profiles=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanInternetProfileFromService(
        Windows::Networking::UX::Internal::MBCategory *this)
{
  _DWORD *v2; // r12
  int ProfileList; // eax
  signed int v4; // r15d
  unsigned int v5; // edi
  unsigned int *i; // rbx
  __int64 v7; // rsi
  const wchar_t *v8; // rbx
  int ProfileIstream; // eax
  const wchar_t *v10; // r14
  int v12; // [rsp+20h] [rbp-E0h]
  unsigned int *v13; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v14; // [rsp+78h] [rbp-88h] BYREF
  int v15; // [rsp+7Ch] [rbp-84h]
  void *Src; // [rsp+80h] [rbp-80h] BYREF
  int v17; // [rsp+88h] [rbp-78h] BYREF
  char v18[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v19[19]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int **v20; // [rsp+B8h] [rbp-48h]
  char v21; // [rsp+C0h] [rbp-40h]
  __int128 v22; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v23[19]; // [rsp+D8h] [rbp-28h]
  _BYTE v24[4456]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v25; // [rsp+1258h] [rbp+1158h]
  __int64 v26; // [rsp+1268h] [rbp+1168h]
  __int64 v27; // [rsp+1998h] [rbp+1898h]

  v13 = 0;
  v20 = &v13;
  v21 = 1;
  v2 = (_DWORD *)((char *)this + 24);
  ProfileList = WwanGetProfileList(*((_QWORD *)this + 38), (char *)this + 24, 0, &v13);
  v4 = ProfileList;
  if ( ProfileList > 0 )
    v4 = (unsigned __int16)ProfileList | 0x80070000;
  if ( v4 < 0 )
  {
    *(_OWORD *)v18 = 0;
    memset(v19, 0, sizeof(v19));
    StringCchPrintfA(
      v18,
      0x23u,
      "{%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
      *v2,
      *((unsigned __int16 *)v2 + 2),
      *((unsigned __int16 *)v2 + 3),
      *((unsigned __int8 *)v2 + 8),
      *((unsigned __int8 *)v2 + 9),
      *((unsigned __int8 *)v2 + 10),
      *((unsigned __int8 *)v2 + 11),
      *((unsigned __int8 *)v2 + 12),
      *((unsigned __int8 *)v2 + 13),
      *((unsigned __int8 *)v2 + 14),
      *((unsigned __int8 *)v2 + 15));
    v22 = *(_OWORD *)v18;
    *(_OWORD *)v23 = *(_OWORD *)v19;
    *(_DWORD *)&v23[15] = *(_DWORD *)&v19[15];
    MBSettingUXLogging::Error(
      "Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanInternetProfileFromService",
      0x127Cu,
      "Failed to call WwanGetProfileList. HRESULT=0x%x, _guidInterface=%hs",
      v4,
      (const char *)&v22);
  }
  else
  {
    v5 = 0;
    v15 = 0;
    for ( i = v13; v5 < *v13; i = v13 )
    {
      memset_0(v24, 0, 0x18B0u);
      v7 = 129LL * v5;
      v8 = (const wchar_t *)&i[v7 + 1];
      v14 = 0;
      Src = 0;
      v17 = 0;
      ProfileIstream = WwanGetProfileIstream(*((_QWORD *)this + 38), v8, &v17, &v14, &Src);
      v4 = ProfileIstream;
      if ( ProfileIstream > 0 )
        v4 = (unsigned __int16)ProfileIstream | 0x80070000;
      if ( v4 >= 0 )
      {
        if ( v14 >= 0x18D8 )
        {
          memcpy_0(v24, Src, 0x18B0u);
          v25 = 0;
          v26 = 0;
          v27 = 0;
          WwanFreeMemory(Src);
          v4 = 0;
        }
        else
        {
          MBSettingUXLogging::Error(
            "Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService",
            0x11CEu,
            "WwanGetProfileIstream returned bad size. HRESULT=0x%x, profileName=%ls, dwWwanDataSize=%d",
            v4,
            v8,
            v14);
          WwanFreeMemory(Src);
          v4 = -2147467259;
        }
      }
      else
      {
        MBSettingUXLogging::Error(
          "Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService",
          0x11C3u,
          "Failed to call WwanGetProfileIstream. profileName=%ls, HRESULT=0x%x",
          v8,
          v4);
        WwanFreeMemory(Src);
      }
      if ( v4 >= 0 )
      {
        MBSettingUXLogging::Info(
          "Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanInternetProfileFromService",
          0x1271u,
          "UpdateWwanProfile");
        LOBYTE(v12) = 0;
        Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile(this, v24, 3, 0, v12);
      }
      else
      {
        v10 = (const wchar_t *)&v13[v7 + 1];
        *(_OWORD *)v18 = 0;
        memset(v19, 0, sizeof(v19));
        StringCchPrintfA(
          v18,
          0x23u,
          "{%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
          *v2,
          *((unsigned __int16 *)this + 14),
          *((unsigned __int16 *)this + 15),
          *((unsigned __int8 *)this + 32),
          *((unsigned __int8 *)this + 33),
          *((unsigned __int8 *)this + 34),
          *((unsigned __int8 *)this + 35),
          *((unsigned __int8 *)this + 36),
          *((unsigned __int8 *)this + 37),
          *((unsigned __int8 *)this + 38),
          *((unsigned __int8 *)this + 39));
        v22 = *(_OWORD *)v18;
        *(_OWORD *)v23 = *(_OWORD *)v19;
        *(_DWORD *)&v23[15] = *(_DWORD *)&v19[15];
        MBSettingUXLogging::Error(
          "Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanInternetProfileFromService",
          0x126Du,
          "_ReadWwanProfileFromService failed. HRESULT=0x%x, _guidInterface=%hs, profileName=%ls",
          v4,
          (const char *)&v22,
          v10);
        v5 = v15;
      }
      v15 = ++v5;
    }
  }
  MBSettingUXLogging::Info(
    "Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanInternetProfileFromService",
    0x127Fu,
    "Complete. profiles=%d",
    *((_DWORD *)this + 234));
  WwanFreeMemory(v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800075a8  push    rbp
0x1800075aa  push    rbx
0x1800075ab  push    rsi
0x1800075ac  push    rdi
0x1800075ad  push    r12
0x1800075af  push    r13
0x1800075b1  push    r14
0x1800075b3  push    r15
0x1800075b5  lea     rbp, [rsp-18B8h]
0x1800075bd  mov     eax, 19B8h
0x1800075c2  call    _alloca_probe
0x1800075c7  sub     rsp, rax
0x1800075ca  mov     rax, cs:__security_cookie
0x1800075d1  xor     rax, rsp
0x1800075d4  mov     [rbp+18F0h+var_50], rax
0x1800075db  mov     r13, rcx
0x1800075de  xor     r14d, r14d
0x1800075e1  mov     [rsp+19F0h+var_1980], r14
0x1800075e6  lea     rax, [rsp+19F0h+var_1980]
0x1800075eb  mov     [rbp+18F0h+var_1938], rax
0x1800075ef  mov     [rbp+18F0h+var_1930], 1
0x1800075f3  lea     r12, [rcx+18h]
0x1800075f7  lea     r9, [rsp+19F0h+var_1980]
0x1800075fc  xor     r8d, r8d
0x1800075ff  mov     rdx, r12
0x180007602  mov     rcx, [rcx+130h]
0x180007609  call    cs:__imp_WwanGetProfileList
0x18000760f  mov     r15d, eax
0x180007612  test    eax, eax
0x180007614  jle     short loc_180007621
0x180007616  movzx   r15d, ax
0x18000761a  or      r15d, 80070000h
0x180007621  test    r15d, r15d
0x180007624  js      loc_180007875
0x18000762a  mov     edi, r14d
0x18000762d  mov     [rsp+19F0h+var_1974], r14d
0x180007632  mov     rbx, [rsp+19F0h+var_1980]
0x180007637  cmp     [rbx], r14d
0x18000763a  jbe     loc_180007940
0x180007640  xor     edx, edx; Val
0x180007642  mov     r8d, 18B0h; Size
0x180007648  lea     rcx, [rbp+18F0h+var_1900]; void *
0x18000764c  call    memset_0
0x180007651  mov     eax, edi
0x180007653  imul    rsi, rax, 204h
0x18000765a  add     rbx, 4
0x18000765e  add     rbx, rsi
0x180007661  mov     [rsp+19F0h+var_1978], r14d
0x180007666  mov     [rbp+18F0h+Src], r14
0x18000766a  mov     [rbp+18F0h+var_1968], r14d
0x18000766e  lea     rax, [rbp+18F0h+Src]
0x180007672  mov     [rsp+19F0h+var_19D0], rax
0x180007677  lea     r9, [rsp+19F0h+var_1978]
0x18000767c  lea     r8, [rbp+18F0h+var_1968]
0x180007680  mov     rdx, rbx
0x180007683  mov     rcx, [r13+130h]
0x18000768a  call    cs:__imp_WwanGetProfileIstream
0x180007690  mov     r15d, eax
0x180007693  test    eax, eax
0x180007695  jle     short loc_1800076A2
0x180007697  movzx   r15d, ax
0x18000769b  or      r15d, 80070000h
0x1800076a2  test    r15d, r15d
0x1800076a5  jns     short loc_1800076D3
0x1800076a7  mov     dword ptr [rsp+19F0h+var_19D0], r15d
0x1800076ac  mov     r9, rbx
0x1800076af  lea     r8, aFailedToCallWw_4; "Failed to call WwanGetProfileIstream. p"...
0x1800076b6  mov     edx, 11C3h; unsigned int
0x1800076bb  lea     rcx, aWindowsNetwork_186; "Windows::Networking::UX::Internal::MBCa"...
0x1800076c2  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x1800076c7  mov     rcx, [rbp+18F0h+Src]
0x1800076cb  call    cs:__imp_WwanFreeMemory
0x1800076d1  jmp     short loc_180007749
0x1800076d3  mov     eax, [rsp+19F0h+var_1978]
0x1800076d7  cmp     eax, 18D8h
0x1800076dc  jnb     short loc_180007714
0x1800076de  mov     dword ptr [rsp+19F0h+var_19C8], eax
0x1800076e2  mov     [rsp+19F0h+var_19D0], rbx
0x1800076e7  mov     r9d, r15d
0x1800076ea  lea     r8, aWwangetprofile_3; "WwanGetProfileIstream returned bad size"...
0x1800076f1  mov     edx, 11CEh; unsigned int
0x1800076f6  lea     rcx, aWindowsNetwork_186; "Windows::Networking::UX::Internal::MBCa"...
0x1800076fd  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x180007702  mov     rcx, [rbp+18F0h+Src]
0x180007706  call    cs:__imp_WwanFreeMemory
0x18000770c  mov     r15d, 80004005h
0x180007712  jmp     short loc_180007749
0x180007714  mov     r8d, 18B0h; Size
0x18000771a  mov     rdx, [rbp+18F0h+Src]; Src
0x18000771e  lea     rcx, [rbp+18F0h+var_1900]; void *
0x180007722  call    memcpy_0
0x180007727  mov     [rbp+18F0h+var_798], r14
0x18000772e  mov     [rbp+18F0h+var_788], r14
0x180007735  mov     [rbp+18F0h+var_58], r14
0x18000773c  mov     rcx, [rbp+18F0h+Src]
0x180007740  call    cs:__imp_WwanFreeMemory
0x180007746  mov     r15d, r14d
0x180007749  test    r15d, r15d
0x18000774c  jns     loc_18000782D
0x180007752  mov     r14, [rsp+19F0h+var_1980]
0x180007757  add     r14, 4
0x18000775b  add     r14, rsi
0x18000775e  xorps   xmm0, xmm0
0x180007761  xor     eax, eax
0x180007763  movups  xmmword ptr [rbp+18F0h+var_1960], xmm0
0x180007767  movups  xmmword ptr [rbp+18F0h+var_1950], xmm0
0x18000776b  mov     dword ptr [rbp+18F0h+var_1950+0Fh], eax
0x18000776e  movzx   eax, byte ptr [r13+27h]
0x180007773  movzx   ecx, byte ptr [r13+26h]
0x180007778  movzx   edx, byte ptr [r13+25h]
0x18000777d  movzx   r8d, byte ptr [r13+24h]
0x180007782  movzx   r9d, byte ptr [r13+23h]
0x180007787  movzx   r10d, byte ptr [r13+22h]
0x18000778c  movzx   r11d, byte ptr [r13+21h]
0x180007791  movzx   ebx, byte ptr [r13+20h]
0x180007796  movzx   edi, word ptr [r13+1Eh]
0x18000779b  movzx   esi, word ptr [r13+1Ch]
0x1800077a0  mov     [rsp+19F0h+var_1988], eax
0x1800077a4  mov     [rsp+19F0h+var_1990], ecx
0x1800077a8  mov     [rsp+19F0h+var_1998], edx
0x1800077ac  mov     [rsp+19F0h+var_19A0], r8d
0x1800077b1  mov     [rsp+19F0h+var_19A8], r9d
0x1800077b6  mov     [rsp+19F0h+var_19B0], r10d
0x1800077bb  mov     [rsp+19F0h+var_19B8], r11d
0x1800077c0  mov     [rsp+19F0h+var_19C0], ebx
0x1800077c4  mov     dword ptr [rsp+19F0h+var_19C8], edi
0x1800077c8  mov     dword ptr [rsp+19F0h+var_19D0], esi
0x1800077cc  mov     r9d, [r12]
0x1800077d0  lea     r8, a08lx04hx04hx02; "{%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%"...
0x1800077d7  mov     edx, 23h ; '#'; unsigned __int64
0x1800077dc  lea     rcx, [rbp+18F0h+var_1960]; char *
0x1800077e0  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800077e5  movups  xmm0, xmmword ptr [rbp+18F0h+var_1960]
0x1800077e9  movups  [rbp+18F0h+var_1928], xmm0
0x1800077ed  movups  xmm1, xmmword ptr [rbp+18F0h+var_1950]
0x1800077f1  movups  xmmword ptr [rbp+18F0h+var_1918], xmm1
0x1800077f5  mov     eax, dword ptr [rbp+18F0h+var_1950+0Fh]
0x1800077f8  mov     dword ptr [rbp+18F0h+var_1918+0Fh], eax
0x1800077fb  mov     [rsp+19F0h+var_19C8], r14
0x180007800  lea     rax, [rbp+18F0h+var_1928]
0x180007804  mov     [rsp+19F0h+var_19D0], rax
0x180007809  mov     r9d, r15d
0x18000780c  lea     r8, aReadwwanprofil_0; "_ReadWwanProfileFromService failed. HRE"...
0x180007813  mov     edx, 126Dh; unsigned int
0x180007818  lea     rcx, aWindowsNetwork_170; "Windows::Networking::UX::Internal::MBCa"...
0x18000781f  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x180007824  mov     edi, [rsp+19F0h+var_1974]
0x180007828  xor     r14d, r14d
0x18000782b  jmp     short loc_18000785D
0x18000782d  lea     r8, aUpdatewwanprof; "UpdateWwanProfile"
0x180007834  mov     edx, 1271h; unsigned int
0x180007839  lea     rcx, aWindowsNetwork_170; "Windows::Networking::UX::Internal::MBCa"...
0x180007840  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180007845  mov     byte ptr [rsp+19F0h+var_19D0], r14b
0x18000784a  xor     r9d, r9d
0x18000784d  lea     r8d, [r9+3]
0x180007851  lea     rdx, [rbp+18F0h+var_1900]
0x180007855  mov     rcx, r13
0x180007858  call    ?tp_UpdateWwanProfile@MBCategory@Internal@UX@Networking@Windows@@AEAAXAEBUWWAN_PROFILE@@W4_WWAN_ACTIVATION_STATE@@_N2@Z; Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile(WWAN_PROFILE const &,_WWAN_ACTIVATION_STATE,bool,bool)
0x18000785d  inc     edi
0x18000785f  mov     [rsp+19F0h+var_1974], edi
0x180007863  mov     rbx, [rsp+19F0h+var_1980]
0x180007868  cmp     edi, [rbx]
0x18000786a  jb      loc_180007640
0x180007870  jmp     loc_180007940
0x180007875  xorps   xmm0, xmm0
0x180007878  xor     eax, eax
0x18000787a  movups  xmmword ptr [rbp+18F0h+var_1960], xmm0
0x18000787e  movups  xmmword ptr [rbp+18F0h+var_1950], xmm0
0x180007882  mov     dword ptr [rbp+18F0h+var_1950+0Fh], eax
0x180007885  movzx   eax, byte ptr [r12+0Fh]
0x18000788b  movzx   ecx, byte ptr [r12+0Eh]
0x180007891  movzx   edx, byte ptr [r12+0Dh]
0x180007897  movzx   r8d, byte ptr [r12+0Ch]
0x18000789d  movzx   r10d, byte ptr [r12+0Bh]
0x1800078a3  movzx   r11d, byte ptr [r12+0Ah]
0x1800078a9  movzx   ebx, byte ptr [r12+9]
0x1800078af  movzx   edi, byte ptr [r12+8]
0x1800078b5  movzx   esi, word ptr [r12+6]
0x1800078bb  movzx   r14d, word ptr [r12+4]
0x1800078c1  mov     [rsp+19F0h+var_1988], eax
0x1800078c5  mov     [rsp+19F0h+var_1990], ecx
0x1800078c9  mov     [rsp+19F0h+var_1998], edx
0x1800078cd  mov     [rsp+19F0h+var_19A0], r8d
0x1800078d2  mov     [rsp+19F0h+var_19A8], r10d
0x1800078d7  mov     [rsp+19F0h+var_19B0], r11d
0x1800078dc  mov     [rsp+19F0h+var_19B8], ebx
0x1800078e0  mov     [rsp+19F0h+var_19C0], edi
0x1800078e4  mov     dword ptr [rsp+19F0h+var_19C8], esi
0x1800078e8  mov     dword ptr [rsp+19F0h+var_19D0], r14d
0x1800078ed  mov     r9d, [r12]
0x1800078f1  lea     r8, a08lx04hx04hx02; "{%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%"...
0x1800078f8  mov     edx, 23h ; '#'; unsigned __int64
0x1800078fd  lea     rcx, [rbp+18F0h+var_1960]; char *
0x180007901  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180007906  movups  xmm0, xmmword ptr [rbp+18F0h+var_1960]
0x18000790a  movups  [rbp+18F0h+var_1928], xmm0
0x18000790e  movups  xmm1, xmmword ptr [rbp+18F0h+var_1950]
0x180007912  movups  xmmword ptr [rbp+18F0h+var_1918], xmm1
0x180007916  mov     eax, dword ptr [rbp+18F0h+var_1950+0Fh]
0x180007919  mov     dword ptr [rbp+18F0h+var_1918+0Fh], eax
0x18000791c  lea     rax, [rbp+18F0h+var_1928]
0x180007920  mov     [rsp+19F0h+var_19D0], rax
0x180007925  mov     r9d, r15d
0x180007928  lea     r8, aFailedToCallWw_2; "Failed to call WwanGetProfileList. HRES"...
0x18000792f  mov     edx, 127Ch; unsigned int
0x180007934  lea     rcx, aWindowsNetwork_170; "Windows::Networking::UX::Internal::MBCa"...
0x18000793b  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x180007940  mov     r9d, [r13+3A8h]
0x180007947  lea     r8, aCompleteProfil; "Complete. profiles=%d"
0x18000794e  mov     edx, 127Fh; unsigned int
0x180007953  lea     rcx, aWindowsNetwork_170; "Windows::Networking::UX::Internal::MBCa"...
0x18000795a  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000795f  nop
0x180007960  mov     rcx, [rsp+19F0h+var_1980]
0x180007965  call    cs:__imp_WwanFreeMemory
0x18000796b  mov     eax, r15d
0x18000796e  mov     rcx, [rbp+18F0h+var_50]
0x180007975  xor     rcx, rsp; StackCookie
0x180007978  call    __security_check_cookie
0x18000797d  add     rsp, 19B8h
0x180007984  pop     r15
0x180007986  pop     r14
0x180007988  pop     r13
0x18000798a  pop     r12
0x18000798c  pop     rdi
0x18000798d  pop     rsi
0x18000798e  pop     rbx
0x18000798f  pop     rbp
0x180007990  retn
```
