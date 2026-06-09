# OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsFromCommonClient(ushort const *,ushort const *)

- ea: `0x18004175c`
- end: `0x180041979`
- name: `?DownloadSettingsFromCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG0@Z`
- size: `541`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, wchar_t *String1, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180044ba0`

## callees

- `0x180040d3c`
- `0x1800411a4`
- `0x18004175c`
- `0x180041980`
- `0x180041b50`
- `0x180044760`
- `0x1800502c2`
- `0x180050300`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800418a0`
- `msvcrt!wcsrchr` at `0x1800418a0`
- `msvcrt!_wcsicmp` at `0x1800417cd`
- `msvcrt!_wcsicmp` at `0x1800417cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004191c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041937`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004191c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041937`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004192c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041945`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004192c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041945`

## string_xrefs

- `0x1800417b6`: `settings-win-ppe.data.microsoft.com`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsFromCommonClient(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        wchar_t *String1,
        const unsigned __int16 *a3)
{
  wchar_t *v5; // rdi
  BOOL v6; // r12d
  OneCore::Base::Telemetry::OneSettingsQuery *v7; // rcx
  const unsigned __int16 *v8; // rdx
  int Headers; // ebx
  unsigned int v10; // r8d
  int v11; // r15d
  int v12; // eax
  wchar_t *v13; // rax
  OneCore::Base::Telemetry::OneSettingsQuery *v14; // rcx
  unsigned __int64 v15; // r9
  HANDLE ProcessHeap; // rax
  HANDLE v17; // rax
  unsigned __int16 *v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  void *v22; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *Str; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v24[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v25[264]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v26[512]; // [rsp+480h] [rbp+380h] BYREF

  v22 = 0;
  v20 = 0;
  memset_0(v26, 0, sizeof(v26));
  lpMem = 0;
  Str = 0;
  v5 = 0;
  v25[0] = 0;
  v24[0] = 0;
  v6 = _wcsicmp(String1, L"settings-win-ppe.data.microsoft.com") == 0;
  OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(v7, &v22, &v20);
  Headers = OneCore::Base::Telemetry::OneSettingsQuery::CreateHeaders(this, v8, (unsigned __int16 **)&lpMem);
  if ( Headers >= 0 )
  {
    Headers = OneCore::Base::Telemetry::OneSettingsQuery::AppendQueryString(this, v26, v10);
    if ( Headers >= 0 )
    {
      v11 = v20;
      v12 = OneCore::Base::Telemetry::OneSettingsQuery::PerformCommonClientDownload(
              this,
              (void *)((unsigned __int64)v22 & -(__int64)(v20 != 0)),
              (const unsigned __int16 *)lpMem,
              v26,
              v6,
              0,
              0,
              &Str);
      v5 = Str;
      Headers = v12;
      if ( v12 == -2147024891 && Str && *Str && (*Str != 58 || Str[1]) )
      {
        v13 = wcsrchr(Str, 0x3Au);
        if ( v13 )
          *v13 = 0;
        if ( !OneCore::Base::Telemetry::OneSettingsQuery::GetCredentialsForBasicProxyIfPresent(
                v14,
                v5,
                v24,
                v15,
                v25,
                (unsigned __int64)v19)
          && v24[0] )
        {
          Headers = OneCore::Base::Telemetry::OneSettingsQuery::PerformCommonClientDownload(
                      this,
                      (void *)((unsigned __int64)v22 & -(__int64)(v11 != 0)),
                      (const unsigned __int16 *)lpMem,
                      v26,
                      v6,
                      v24,
                      v25,
                      0);
        }
      }
    }
  }
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  if ( v5 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v5);
  }
  return (unsigned int)Headers;
}

```

## disassembly

```asm
0x18004175c  mov     [rsp-8+arg_10], rbx
0x180041761  mov     [rsp-8+arg_18], rdi
0x180041766  push    rbp
0x180041767  push    r12
0x180041769  push    r13
0x18004176b  push    r14
0x18004176d  push    r15
0x18004176f  lea     rbp, [rsp-790h]
0x180041777  sub     rsp, 890h
0x18004177e  mov     rax, cs:__security_cookie
0x180041785  xor     rax, rsp
0x180041788  mov     [rbp+7B0h+var_30], rax
0x18004178f  mov     rbx, rdx
0x180041792  mov     r14, rcx
0x180041795  xor     r13d, r13d
0x180041798  lea     rcx, [rbp+7B0h+var_430]; void *
0x18004179f  xor     edx, edx; Val
0x1800417a1  mov     [rsp+8B0h+var_860], r13
0x1800417a6  mov     r8d, 400h; Size
0x1800417ac  mov     [rsp+8B0h+var_870], r13d
0x1800417b1  call    memset_0
0x1800417b6  lea     rdx, aSettingsWinPpe; "settings-win-ppe.data.microsoft.com"
0x1800417bd  mov     [rsp+8B0h+lpMem], r13
0x1800417c2  mov     rcx, rbx; String1
0x1800417c5  mov     [rsp+8B0h+Str], r13
0x1800417ca  mov     edi, r13d
0x1800417cd  call    cs:__imp__wcsicmp
0x1800417d3  mov     r12d, r13d
0x1800417d6  mov     [rbp+7B0h+var_640], r13w
0x1800417de  test    eax, eax
0x1800417e0  mov     [rsp+8B0h+var_850], r13w
0x1800417e6  lea     r8, [rsp+8B0h+var_870]; int *
0x1800417eb  lea     rdx, [rsp+8B0h+var_860]; void **
0x1800417f0  setz    r12b
0x1800417f4  call    ?FindUserSession@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAH@Z; OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(void * *,int *)
0x1800417f9  lea     r8, [rsp+8B0h+lpMem]; unsigned __int16 **
0x1800417fe  mov     rcx, r14; this
0x180041801  call    ?CreateHeaders@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAPEAG@Z; OneCore::Base::Telemetry::OneSettingsQuery::CreateHeaders(ushort const *,ushort * *)
0x180041806  mov     ebx, eax
0x180041808  test    eax, eax
0x18004180a  js      loc_180041915
0x180041810  lea     rdx, [rbp+7B0h+var_430]; unsigned __int16 *
0x180041817  mov     rcx, r14; this
0x18004181a  call    ?AppendQueryString@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAGK@Z; OneCore::Base::Telemetry::OneSettingsQuery::AppendQueryString(ushort *,ulong)
0x18004181f  mov     ebx, eax
0x180041821  test    eax, eax
0x180041823  js      loc_180041915
0x180041829  mov     r15d, [rsp+8B0h+var_870]
0x18004182e  lea     r9, [rbp+7B0h+var_430]; unsigned __int16 *
0x180041835  mov     r8, [rsp+8B0h+lpMem]; unsigned __int16 *
0x18004183a  mov     eax, r15d
0x18004183d  neg     eax
0x18004183f  mov     rcx, r14; this
0x180041842  lea     rax, [rsp+8B0h+Str]
0x180041847  mov     [rsp+8B0h+var_878], rax; unsigned __int16 **
0x18004184c  sbb     rdx, rdx
0x18004184f  and     rdx, [rsp+8B0h+var_860]; void *
0x180041854  mov     [rsp+8B0h+var_880], r13; unsigned __int16 *
0x180041859  mov     [rsp+8B0h+var_888], r13; unsigned __int64
0x18004185e  mov     dword ptr [rsp+8B0h+var_890], r12d; int
0x180041863  call    ?PerformCommonClientDownload@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAXPEBG1H11PEAPEAG@Z; OneCore::Base::Telemetry::OneSettingsQuery::PerformCommonClientDownload(void *,ushort const *,ushort const *,int,ushort const *,ushort const *,ushort * *)
0x180041868  mov     rdi, [rsp+8B0h+Str]
0x18004186d  mov     ebx, eax
0x18004186f  cmp     eax, 80070005h
0x180041874  jnz     loc_180041915
0x18004187a  test    rdi, rdi
0x18004187d  jz      loc_180041915
0x180041883  cmp     [rdi], r13w
0x180041887  jz      loc_180041915
0x18004188d  lea     edx, [r13+3Ah]; Ch
0x180041891  cmp     [rdi], dx
0x180041894  jnz     short loc_18004189D
0x180041896  cmp     [rdi+2], r13w
0x18004189b  jz      short loc_180041915
0x18004189d  mov     rcx, rdi; Str
0x1800418a0  call    cs:__imp_wcsrchr
0x1800418a6  test    rax, rax
0x1800418a9  jz      short loc_1800418AF
0x1800418ab  mov     [rax], r13w
0x1800418af  lea     rax, [rbp+7B0h+var_640]
0x1800418b6  mov     rdx, rdi; unsigned __int16 *
0x1800418b9  lea     r8, [rsp+8B0h+var_850]; unsigned __int16 *
0x1800418be  mov     [rsp+8B0h+var_890], rax; unsigned __int16 *
0x1800418c3  call    ?GetCredentialsForBasicProxyIfPresent@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAG_K12@Z; OneCore::Base::Telemetry::OneSettingsQuery::GetCredentialsForBasicProxyIfPresent(ushort const *,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x1800418c8  test    eax, eax
0x1800418ca  jnz     short loc_180041915
0x1800418cc  cmp     r13w, [rsp+8B0h+var_850]
0x1800418d2  jz      short loc_180041915
0x1800418d4  mov     r8, [rsp+8B0h+lpMem]; unsigned __int16 *
0x1800418d9  lea     rax, [rbp+7B0h+var_640]
0x1800418e0  mov     [rsp+8B0h+var_878], r13; unsigned __int16 **
0x1800418e5  lea     r9, [rbp+7B0h+var_430]; unsigned __int16 *
0x1800418ec  mov     [rsp+8B0h+var_880], rax; unsigned __int16 *
0x1800418f1  neg     r15d
0x1800418f4  lea     rax, [rsp+8B0h+var_850]
0x1800418f9  mov     rcx, r14; this
0x1800418fc  sbb     rdx, rdx
0x1800418ff  mov     [rsp+8B0h+var_888], rax; unsigned __int16 *
0x180041904  and     rdx, [rsp+8B0h+var_860]; void *
0x180041909  mov     dword ptr [rsp+8B0h+var_890], r12d; int
0x18004190e  call    ?PerformCommonClientDownload@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAXPEBG1H11PEAPEAG@Z; OneCore::Base::Telemetry::OneSettingsQuery::PerformCommonClientDownload(void *,ushort const *,ushort const *,int,ushort const *,ushort const *,ushort * *)
0x180041913  mov     ebx, eax
0x180041915  cmp     [rsp+8B0h+lpMem], r13
0x18004191a  jz      short loc_180041932
0x18004191c  call    cs:__imp_GetProcessHeap
0x180041922  mov     r8, [rsp+8B0h+lpMem]; lpMem
0x180041927  xor     edx, edx; dwFlags
0x180041929  mov     rcx, rax; hHeap
0x18004192c  call    cs:__imp_HeapFree
0x180041932  test    rdi, rdi
0x180041935  jz      short loc_18004194B
0x180041937  call    cs:__imp_GetProcessHeap
0x18004193d  mov     r8, rdi; lpMem
0x180041940  xor     edx, edx; dwFlags
0x180041942  mov     rcx, rax; hHeap
0x180041945  call    cs:__imp_HeapFree
0x18004194b  mov     eax, ebx
0x18004194d  mov     rcx, [rbp+7B0h+var_30]
0x180041954  xor     rcx, rsp; StackCookie
0x180041957  call    __security_check_cookie
0x18004195c  lea     r11, [rsp+8B0h+var_20]
0x180041964  mov     rbx, [r11+40h]
0x180041968  mov     rdi, [r11+48h]
0x18004196c  mov     rsp, r11
0x18004196f  pop     r15
0x180041971  pop     r14
0x180041973  pop     r13
0x180041975  pop     r12
0x180041977  pop     rbp
0x180041978  retn
```
