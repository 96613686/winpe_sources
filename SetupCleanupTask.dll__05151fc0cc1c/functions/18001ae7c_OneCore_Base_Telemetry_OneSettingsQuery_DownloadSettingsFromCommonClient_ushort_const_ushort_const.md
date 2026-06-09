# OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsFromCommonClient(ushort const *,ushort const *)

- ea: `0x18001ae7c`
- end: `0x18001b099`
- name: `?DownloadSettingsFromCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG0@Z`
- size: `541`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, wchar_t *String1, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f3f4`

## callees

- `0x18001a1e4`
- `0x18001a878`
- `0x18001ae7c`
- `0x18001b524`
- `0x18001b8ec`
- `0x18001ef10`
- `0x1800322d2`
- `0x180032310`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001aeed`
- `msvcrt!_wcsicmp` at `0x18001aeed`
- `msvcrt!wcsrchr` at `0x18001afc0`
- `msvcrt!wcsrchr` at `0x18001afc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b03c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b057`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b03c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b057`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b04c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b065`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b04c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b065`

## string_xrefs

- `0x18001aed6`: `settings-win-ppe.data.microsoft.com`

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
0x18001ae7c  mov     [rsp-8+arg_10], rbx
0x18001ae81  mov     [rsp-8+arg_18], rdi
0x18001ae86  push    rbp
0x18001ae87  push    r12
0x18001ae89  push    r13
0x18001ae8b  push    r14
0x18001ae8d  push    r15
0x18001ae8f  lea     rbp, [rsp-790h]
0x18001ae97  sub     rsp, 890h
0x18001ae9e  mov     rax, cs:__security_cookie
0x18001aea5  xor     rax, rsp
0x18001aea8  mov     [rbp+7B0h+var_30], rax
0x18001aeaf  mov     rbx, rdx
0x18001aeb2  mov     r14, rcx
0x18001aeb5  xor     r13d, r13d
0x18001aeb8  lea     rcx, [rbp+7B0h+var_430]; void *
0x18001aebf  xor     edx, edx; Val
0x18001aec1  mov     [rsp+8B0h+var_860], r13
0x18001aec6  mov     r8d, 400h; Size
0x18001aecc  mov     [rsp+8B0h+var_870], r13d
0x18001aed1  call    memset_0
0x18001aed6  lea     rdx, aSettingsWinPpe; "settings-win-ppe.data.microsoft.com"
0x18001aedd  mov     [rsp+8B0h+lpMem], r13
0x18001aee2  mov     rcx, rbx; String1
0x18001aee5  mov     [rsp+8B0h+Str], r13
0x18001aeea  mov     edi, r13d
0x18001aeed  call    cs:__imp__wcsicmp
0x18001aef3  mov     r12d, r13d
0x18001aef6  mov     [rbp+7B0h+var_640], r13w
0x18001aefe  test    eax, eax
0x18001af00  mov     [rsp+8B0h+var_850], r13w
0x18001af06  lea     r8, [rsp+8B0h+var_870]; int *
0x18001af0b  lea     rdx, [rsp+8B0h+var_860]; void **
0x18001af10  setz    r12b
0x18001af14  call    ?FindUserSession@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAH@Z; OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(void * *,int *)
0x18001af19  lea     r8, [rsp+8B0h+lpMem]; unsigned __int16 **
0x18001af1e  mov     rcx, r14; this
0x18001af21  call    ?CreateHeaders@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAPEAG@Z; OneCore::Base::Telemetry::OneSettingsQuery::CreateHeaders(ushort const *,ushort * *)
0x18001af26  mov     ebx, eax
0x18001af28  test    eax, eax
0x18001af2a  js      loc_18001B035
0x18001af30  lea     rdx, [rbp+7B0h+var_430]; unsigned __int16 *
0x18001af37  mov     rcx, r14; this
0x18001af3a  call    ?AppendQueryString@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAGK@Z; OneCore::Base::Telemetry::OneSettingsQuery::AppendQueryString(ushort *,ulong)
0x18001af3f  mov     ebx, eax
0x18001af41  test    eax, eax
0x18001af43  js      loc_18001B035
0x18001af49  mov     r15d, [rsp+8B0h+var_870]
0x18001af4e  lea     r9, [rbp+7B0h+var_430]; unsigned __int16 *
0x18001af55  mov     r8, [rsp+8B0h+lpMem]; unsigned __int16 *
0x18001af5a  mov     eax, r15d
0x18001af5d  neg     eax
0x18001af5f  mov     rcx, r14; this
0x18001af62  lea     rax, [rsp+8B0h+Str]
0x18001af67  mov     [rsp+8B0h+var_878], rax; unsigned __int16 **
0x18001af6c  sbb     rdx, rdx
0x18001af6f  and     rdx, [rsp+8B0h+var_860]; void *
0x18001af74  mov     [rsp+8B0h+var_880], r13; unsigned __int16 *
0x18001af79  mov     [rsp+8B0h+var_888], r13; unsigned __int64
0x18001af7e  mov     dword ptr [rsp+8B0h+var_890], r12d; int
0x18001af83  call    ?PerformCommonClientDownload@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAXPEBG1H11PEAPEAG@Z; OneCore::Base::Telemetry::OneSettingsQuery::PerformCommonClientDownload(void *,ushort const *,ushort const *,int,ushort const *,ushort const *,ushort * *)
0x18001af88  mov     rdi, [rsp+8B0h+Str]
0x18001af8d  mov     ebx, eax
0x18001af8f  cmp     eax, 80070005h
0x18001af94  jnz     loc_18001B035
0x18001af9a  test    rdi, rdi
0x18001af9d  jz      loc_18001B035
0x18001afa3  cmp     [rdi], r13w
0x18001afa7  jz      loc_18001B035
0x18001afad  lea     edx, [r13+3Ah]; Ch
0x18001afb1  cmp     [rdi], dx
0x18001afb4  jnz     short loc_18001AFBD
0x18001afb6  cmp     [rdi+2], r13w
0x18001afbb  jz      short loc_18001B035
0x18001afbd  mov     rcx, rdi; Str
0x18001afc0  call    cs:__imp_wcsrchr
0x18001afc6  test    rax, rax
0x18001afc9  jz      short loc_18001AFCF
0x18001afcb  mov     [rax], r13w
0x18001afcf  lea     rax, [rbp+7B0h+var_640]
0x18001afd6  mov     rdx, rdi; unsigned __int16 *
0x18001afd9  lea     r8, [rsp+8B0h+var_850]; unsigned __int16 *
0x18001afde  mov     [rsp+8B0h+var_890], rax; unsigned __int16 *
0x18001afe3  call    ?GetCredentialsForBasicProxyIfPresent@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAG_K12@Z; OneCore::Base::Telemetry::OneSettingsQuery::GetCredentialsForBasicProxyIfPresent(ushort const *,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x18001afe8  test    eax, eax
0x18001afea  jnz     short loc_18001B035
0x18001afec  cmp     r13w, [rsp+8B0h+var_850]
0x18001aff2  jz      short loc_18001B035
0x18001aff4  mov     r8, [rsp+8B0h+lpMem]; unsigned __int16 *
0x18001aff9  lea     rax, [rbp+7B0h+var_640]
0x18001b000  mov     [rsp+8B0h+var_878], r13; unsigned __int16 **
0x18001b005  lea     r9, [rbp+7B0h+var_430]; unsigned __int16 *
0x18001b00c  mov     [rsp+8B0h+var_880], rax; unsigned __int16 *
0x18001b011  neg     r15d
0x18001b014  lea     rax, [rsp+8B0h+var_850]
0x18001b019  mov     rcx, r14; this
0x18001b01c  sbb     rdx, rdx
0x18001b01f  mov     [rsp+8B0h+var_888], rax; unsigned __int16 *
0x18001b024  and     rdx, [rsp+8B0h+var_860]; void *
0x18001b029  mov     dword ptr [rsp+8B0h+var_890], r12d; int
0x18001b02e  call    ?PerformCommonClientDownload@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAXPEBG1H11PEAPEAG@Z; OneCore::Base::Telemetry::OneSettingsQuery::PerformCommonClientDownload(void *,ushort const *,ushort const *,int,ushort const *,ushort const *,ushort * *)
0x18001b033  mov     ebx, eax
0x18001b035  cmp     [rsp+8B0h+lpMem], r13
0x18001b03a  jz      short loc_18001B052
0x18001b03c  call    cs:__imp_GetProcessHeap
0x18001b042  mov     r8, [rsp+8B0h+lpMem]; lpMem
0x18001b047  xor     edx, edx; dwFlags
0x18001b049  mov     rcx, rax; hHeap
0x18001b04c  call    cs:__imp_HeapFree
0x18001b052  test    rdi, rdi
0x18001b055  jz      short loc_18001B06B
0x18001b057  call    cs:__imp_GetProcessHeap
0x18001b05d  mov     r8, rdi; lpMem
0x18001b060  xor     edx, edx; dwFlags
0x18001b062  mov     rcx, rax; hHeap
0x18001b065  call    cs:__imp_HeapFree
0x18001b06b  mov     eax, ebx
0x18001b06d  mov     rcx, [rbp+7B0h+var_30]
0x18001b074  xor     rcx, rsp; StackCookie
0x18001b077  call    __security_check_cookie
0x18001b07c  lea     r11, [rsp+8B0h+var_20]
0x18001b084  mov     rbx, [r11+40h]
0x18001b088  mov     rdi, [r11+48h]
0x18001b08c  mov     rsp, r11
0x18001b08f  pop     r15
0x18001b091  pop     r14
0x18001b093  pop     r13
0x18001b095  pop     r12
0x18001b097  pop     rbp
0x18001b098  retn
```
