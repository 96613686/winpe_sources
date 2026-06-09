# SbGetUEFIEncodedInfo(SBUEFICensusInfo *,int *)

- ea: `0x180057a18`
- end: `0x180057c18`
- name: `?SbGetUEFIEncodedInfo@@YAJPEAUSBUEFICensusInfo@@PEAH@Z`
- size: `512`
- prototype: `__int64 __fastcall(struct SBUEFICensusInfo *, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x180057c20`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x180037a04`
- `0x18003a128`
- `0x18003c0b8`
- `0x180056f5c`
- `0x180057130`
- `0x1800572e4`
- `0x180057644`
- `0x1800577f8`
- `0x1800578f8`
- `0x180057a18`
- `0x180057ca0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180057b93`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180057b93`

## string_xrefs

- `0x180057b37`: `All required keys are updated`
- `0x180057b43`: `Updated`
- `0x180057bbc`: `Updates NotStarted`
- `0x180057b5f`: `AvailableUpdates`
- `0x180057ba2`: `Rolling updates are in progress`

## pseudocode

```c
__int64 __fastcall SbGetUEFIEncodedInfo(struct SBUEFICensusInfo *a1, int *a2)
{
  int v2; // ebx
  int PKEncoding; // esi
  int KEKEncoding; // eax
  int DBEncoding; // eax
  int DBXEncoding; // eax
  __int128 v9; // xmm8
  __int128 v10; // xmm9
  __int128 v11; // xmm10
  __m128i v12; // xmm6
  __int128 v13; // xmm7
  BYTE *v14; // rcx
  int pvData; // [rsp+48h] [rbp-79h] BYREF
  DWORD pcbData[3]; // [rsp+4Ch] [rbp-75h] BYREF
  __m128i v18; // [rsp+58h] [rbp-69h] BYREF
  __int128 v19; // [rsp+68h] [rbp-59h]
  __int128 v20; // [rsp+78h] [rbp-49h]
  _OWORD v21[2]; // [rsp+88h] [rbp-39h]

  v2 = 0;
  pvData = 0;
  memset_0(&v18, 0, 0x4Eu);
  v18.m128i_i8[0] = 6;
  PKEncoding = GetPKEncoding(&v18.m128i_i8[1]);
  KEKEncoding = GetKEKEncoding(&v18.m128i_u8[5]);
  if ( PKEncoding >= 0 )
    PKEncoding = KEKEncoding;
  DBEncoding = GetDBEncoding((char *)&v18.m128i_u32[1] + 3);
  if ( PKEncoding >= 0 )
    PKEncoding = DBEncoding;
  DBXEncoding = GetDBXEncoding((char *)&v18.m128i_u64[1] + 1);
  v9 = v21[0];
  v10 = v20;
  v11 = v19;
  v12 = v18;
  v13 = *(_OWORD *)((char *)v21 + 14);
  if ( PKEncoding >= 0 )
  {
    PKEncoding = DBXEncoding;
    if ( DBXEncoding >= 0 )
    {
      *(__m128i *)a1 = v18;
      *((_OWORD *)a1 + 1) = v11;
      *((_OWORD *)a1 + 2) = v10;
      *((_OWORD *)a1 + 3) = v9;
      *(_OWORD *)((char *)a1 + 62) = v13;
    }
  }
  if ( (_mm_cvtsi128_si32(_mm_srli_si128(v12, 7)) & 0x10) != 0 )
  {
    v2 = 1;
    if ( (int)IsBootManagerSignedWithPCA2023(&pvData) >= 0 )
    {
      if ( pvData )
        v2 = 2;
    }
  }
  SetWindowsUEFICA2023CapableRegistry(v2);
  v21[0] = v9;
  v18 = v12;
  v19 = v11;
  v20 = v10;
  *(_OWORD *)((char *)v21 + 14) = v13;
  if ( (unsigned int)HaveAllRequiredKeysUpdated(&v18, a2) )
  {
    SBServicingLogMessage((wchar_t *)L"All required keys are updated");
    v14 = (BYTE *)L"Updated";
LABEL_17:
    SetUEFICA2023Status(v14);
    DeleteUEFICA2023Error();
    return (unsigned int)PKEncoding;
  }
  pvData = 0;
  pcbData[0] = 4;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot",
    L"AvailableUpdates",
    0x18u,
    0,
    &pvData,
    pcbData);
  if ( (pvData & 0x1944) == 0 )
  {
    SBServicingLogMessage((wchar_t *)L"Updates NotStarted");
    v14 = (BYTE *)L"NotStarted";
    goto LABEL_17;
  }
  SBServicingLogMessage((wchar_t *)L"Rolling updates are in progress");
  SetUEFICA2023Status((BYTE *)L"InProgress");
  return (unsigned int)PKEncoding;
}

```

## disassembly

```asm
0x180057a18  mov     rax, rsp
0x180057a1b  mov     [rax+18h], rbx
0x180057a1f  mov     [rax+20h], rsi
0x180057a23  push    rbp
0x180057a24  push    rdi
0x180057a25  push    r14
0x180057a27  lea     rbp, [rax-5Fh]
0x180057a2b  sub     rsp, 100h
0x180057a32  movaps  xmmword ptr [rax-28h], xmm6
0x180057a36  movaps  xmmword ptr [rax-38h], xmm7
0x180057a3a  movaps  xmmword ptr [rax-48h], xmm8
0x180057a3f  movaps  xmmword ptr [rax-58h], xmm9
0x180057a44  movaps  xmmword ptr [rax-68h], xmm10
0x180057a49  mov     rax, cs:__security_cookie
0x180057a50  xor     rax, rsp
0x180057a53  mov     [rbp+57h+var_70], rax
0x180057a57  xor     ebx, ebx
0x180057a59  mov     r14, rdx
0x180057a5c  mov     rdi, rcx
0x180057a5f  mov     [rbp+57h+var_D0], ebx
0x180057a62  xor     edx, edx; Val
0x180057a64  lea     rcx, [rbp+57h+var_C0]; void *
0x180057a68  lea     r8d, [rbx+4Eh]; Size
0x180057a6c  call    memset_0
0x180057a71  lea     rcx, [rbp+57h+var_C0+1]
0x180057a75  mov     byte ptr [rbp+57h+var_C0], 6
0x180057a79  call    GetPKEncoding
0x180057a7e  lea     rcx, [rbp+57h+var_C0+5]
0x180057a82  mov     esi, eax
0x180057a84  call    GetKEKEncoding
0x180057a89  test    esi, esi
0x180057a8b  lea     rcx, [rbp+57h+var_C0+7]
0x180057a8f  cmovns  esi, eax
0x180057a92  call    GetDBEncoding
0x180057a97  test    esi, esi
0x180057a99  lea     rcx, [rbp+57h+var_C0+9]
0x180057a9d  cmovns  esi, eax
0x180057aa0  call    GetDBXEncoding
0x180057aa5  movaps  xmm8, xmmword ptr [rbp+57h+var_90]
0x180057aaa  movaps  xmm9, [rbp+57h+var_A0]
0x180057aaf  movaps  xmm10, [rbp+57h+var_B0]
0x180057ab4  movaps  xmm6, [rbp+57h+var_C0]
0x180057ab8  movups  xmm7, xmmword ptr [rbp+57h+var_90+0Eh]
0x180057abc  test    esi, esi
0x180057abe  js      short loc_180057ADC
0x180057ac0  mov     esi, eax
0x180057ac2  test    eax, eax
0x180057ac4  js      short loc_180057ADC
0x180057ac6  movaps  xmmword ptr [rdi], xmm6
0x180057ac9  movaps  xmmword ptr [rdi+10h], xmm10
0x180057ace  movaps  xmmword ptr [rdi+20h], xmm9
0x180057ad3  movaps  xmmword ptr [rdi+30h], xmm8
0x180057ad8  movups  xmmword ptr [rdi+3Eh], xmm7
0x180057adc  movdqa  xmm0, xmm6
0x180057ae0  psrldq  xmm0, 7
0x180057ae5  movd    eax, xmm0
0x180057ae9  test    al, 10h
0x180057aeb  jz      short loc_180057B09
0x180057aed  lea     rcx, [rbp+57h+var_D0]; int *
0x180057af1  mov     ebx, 1
0x180057af6  call    ?IsBootManagerSignedWithPCA2023@@YAJPEAH@Z; IsBootManagerSignedWithPCA2023(int *)
0x180057afb  test    eax, eax
0x180057afd  js      short loc_180057B09
0x180057aff  cmp     [rbp+57h+var_D0], 0
0x180057b03  lea     eax, [rbx+1]
0x180057b06  cmovnz  ebx, eax
0x180057b09  mov     ecx, ebx; unsigned int
0x180057b0b  call    ?SetWindowsUEFICA2023CapableRegistry@@YAXK@Z; SetWindowsUEFICA2023CapableRegistry(ulong)
0x180057b10  movaps  xmmword ptr [rbp+57h+var_90], xmm8
0x180057b15  lea     rcx, [rbp+57h+var_C0]
0x180057b19  mov     rdx, r14
0x180057b1c  movaps  [rbp+57h+var_C0], xmm6
0x180057b20  movaps  [rbp+57h+var_B0], xmm10
0x180057b25  movaps  [rbp+57h+var_A0], xmm9
0x180057b2a  movups  xmmword ptr [rbp+57h+var_90+0Eh], xmm7
0x180057b2e  call    HaveAllRequiredKeysUpdated
0x180057b33  test    eax, eax
0x180057b35  jz      short loc_180057B4F
0x180057b37  lea     rcx, aAllRequiredKey; "All required keys are updated"
0x180057b3e  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180057b43  lea     rcx, aUpdated; "Updated"
0x180057b4a  jmp     loc_180057BCF
0x180057b4f  lea     rax, [rbp+57h+var_CC]
0x180057b53  mov     [rbp+57h+var_D0], 0
0x180057b5a  mov     [rsp+110h+pcbData], rax; pcbData
0x180057b5f  lea     r8, aAvailableupdat; "AvailableUpdates"
0x180057b66  lea     rax, [rbp+57h+var_D0]
0x180057b6a  mov     [rbp+57h+var_CC], 4
0x180057b71  mov     [rsp+110h+pvData], rax; pvData
0x180057b76  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x180057b7d  mov     r9d, 18h; dwFlags
0x180057b83  mov     [rsp+110h+pdwType], 0; pdwType
0x180057b8c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180057b93  call    cs:__imp_RegGetValueW
0x180057b99  test    [rbp+57h+var_D0], 1944h
0x180057ba0  jz      short loc_180057BBC
0x180057ba2  lea     rcx, aRollingUpdates; "Rolling updates are in progress"
0x180057ba9  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180057bae  lea     rcx, aInprogress; "InProgress"
0x180057bb5  call    SetUEFICA2023Status
0x180057bba  jmp     short loc_180057BD9
0x180057bbc  lea     rcx, aUpdatesNotstar; "Updates NotStarted"
0x180057bc3  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180057bc8  lea     rcx, aNotstarted; "NotStarted"
0x180057bcf  call    SetUEFICA2023Status
0x180057bd4  call    DeleteUEFICA2023Error
0x180057bd9  mov     eax, esi
0x180057bdb  mov     rcx, [rbp+57h+var_70]
0x180057bdf  xor     rcx, rsp; StackCookie
0x180057be2  call    __security_check_cookie
0x180057be7  lea     r11, [rsp+110h+var_10]
0x180057bef  mov     rbx, [r11+30h]
0x180057bf3  mov     rsi, [r11+38h]
0x180057bf7  movaps  xmm6, xmmword ptr [r11-10h]
0x180057bfc  movaps  xmm7, xmmword ptr [r11-20h]
0x180057c01  movaps  xmm8, xmmword ptr [r11-30h]
0x180057c06  movaps  xmm9, xmmword ptr [r11-40h]
0x180057c0b  movaps  xmm10, xmmword ptr [r11-50h]
0x180057c10  mov     rsp, r11
0x180057c13  pop     r14
0x180057c15  pop     rdi
0x180057c16  pop     rbp
0x180057c17  retn
```
