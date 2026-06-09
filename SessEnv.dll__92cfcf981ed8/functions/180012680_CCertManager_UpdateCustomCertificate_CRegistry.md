# CCertManager::UpdateCustomCertificate(CRegistry *)

- ea: `0x180012680`
- end: `0x18001289e`
- name: `?UpdateCustomCertificate@CCertManager@@AEAAJPEAVCRegistry@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(CCertManager *__hidden this, struct CRegistry *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18002b64c`

## callees

- `0x180003f30`
- `0x180004a50`
- `0x180012680`
- `0x18001a280`
- `0x18001a8d0`
- `0x18002a9b8`
- `0x18002b0dc`
- `0x18002c3c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012742`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012742`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800127cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800127cb`

## string_xrefs

- `0x180012761`: `pReg->OpenKey failed: 0x%x in %s`
- `0x18001276b`: `CCertManager::GetHashFromTheRegistry`
- `0x180012833`: `GetHashFromTheRegistry failed: 0x%x in %s`
- `0x180012829`: `CCertManager::UpdateCustomCertificate`
- `0x180012715`: `pReg->ReadRegBinary failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCertManager::UpdateCustomCertificate(CCertManager *this, struct CRegistry *a2)
{
  CRegistry *v4; // rdi
  int v5; // eax
  unsigned __int16 v6; // dx
  unsigned int v7; // r8d
  signed int v8; // ebx
  LSTATUS v9; // eax
  unsigned int v10; // ecx
  CCertManager *v11; // rcx
  CCertManager *v12; // rcx
  unsigned int v14; // [rsp+30h] [rbp-29h] BYREF
  int v15; // [rsp+34h] [rbp-25h] BYREF
  unsigned __int8 *v16; // [rsp+38h] [rbp-21h] BYREF
  void **v17; // [rsp+40h] [rbp-19h] BYREF
  void *Block; // [rsp+48h] [rbp-11h]
  int v19; // [rsp+50h] [rbp-9h]
  HKEY hKey; // [rsp+58h] [rbp-1h] BYREF
  int v21; // [rsp+60h] [rbp+7h]
  int v22; // [rsp+64h] [rbp+Bh]
  unsigned __int8 v23[16]; // [rsp+68h] [rbp+Fh] BYREF
  int v24; // [rsp+78h] [rbp+1Fh]

  v15 = 0;
  v17 = &CRegistry::`vftable';
  Block = 0;
  v19 = 0;
  hKey = 0;
  v21 = -1;
  v22 = -1;
  v16 = 0;
  v14 = 0;
  if ( a2 )
  {
    v4 = a2;
  }
  else
  {
    v4 = (CRegistry *)&v17;
    v9 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
           0,
           0x20019u,
           &hKey);
    v8 = v9;
    if ( v9 )
    {
      hKey = 0;
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
    }
    if ( v8 < 0 )
    {
      _DbgPrintMessage(8, "pReg->OpenKey failed: 0x%x in %s", (unsigned int)v8, "CCertManager::GetHashFromTheRegistry");
      goto LABEL_21;
    }
  }
  v5 = CRegistry::ReadReg(v4, L"SSLCertificateSHA1Hash", &v16, &v14, 3u);
  v8 = v5;
  if ( v5 > 0 )
    v8 = (unsigned __int16)v5 | 0x80070000;
  if ( v8 >= 0 )
  {
    if ( v14 == 20 )
    {
      v10 = 0;
      v6 = (unsigned __int16)v16;
      while ( v10 < 0x14 )
      {
        if ( v16[v10] )
        {
          *(_OWORD *)v23 = *(_OWORD *)v16;
          v24 = *((_DWORD *)v16 + 4);
          goto LABEL_21;
        }
        ++v10;
      }
      v8 = -2147024894;
    }
    else
    {
      v8 = -2147024883;
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "pReg->ReadRegBinary failed: 0x%x in %s",
      (unsigned int)v8,
      "CCertManager::GetHashFromTheRegistry");
  }
LABEL_21:
  v17 = &CRegistry::`vftable';
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( Block )
    operator delete(Block);
  if ( v8 == -2147024894 )
    return 0;
  if ( v8 == -2147024883 )
  {
    CCertManager::SecLogEvent(this, v6, 0xC0000423, 0);
    CCertManager::PutHashInTheRegistry(v11, a2, L"SSLCertificateSHA1Hash", 0, 0);
LABEL_30:
    _DbgPrintMessage(8, "GetHashFromTheRegistry failed: 0x%x in %s", v8, "CCertManager::UpdateCustomCertificate");
    return (unsigned int)v8;
  }
  if ( v8 < 0 )
    goto LABEL_30;
  v8 = CCertManager::ValidateCertAndLogProblems(this, v23, v7, &v15);
  if ( v8 < 0 && !v15 )
    CCertManager::PutHashInTheRegistry(v12, a2, L"SSLCertificateSHA1Hash", 0, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180012680  mov     [rsp-8+arg_10], rbx
0x180012685  push    rbp
0x180012686  push    rsi
0x180012687  push    rdi
0x180012688  push    r14
0x18001268a  push    r15
0x18001268c  lea     rbp, [rsp-37h]
0x180012691  sub     rsp, 90h
0x180012698  mov     rax, cs:__security_cookie
0x18001269f  xor     rax, rsp
0x1800126a2  mov     [rbp+57h+var_30], rax
0x1800126a6  mov     rsi, rdx
0x1800126a9  mov     r14, rcx
0x1800126ac  xor     r15d, r15d
0x1800126af  mov     [rbp+57h+var_7C], r15d
0x1800126b3  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x1800126ba  mov     [rbp+57h+var_70], rax
0x1800126be  mov     [rbp+57h+Block], r15
0x1800126c2  mov     [rbp+57h+var_60], r15d
0x1800126c6  mov     [rbp+57h+hKey], r15
0x1800126ca  or      eax, 0FFFFFFFFh
0x1800126cd  mov     [rbp+57h+var_50], eax
0x1800126d0  mov     [rbp+57h+var_4C], eax
0x1800126d3  mov     [rbp+57h+var_78], r15
0x1800126d7  mov     [rbp+57h+var_80], r15d
0x1800126db  test    rdx, rdx
0x1800126de  jz      short loc_18001271E
0x1800126e0  mov     rdi, rdx
0x1800126e3  mov     dword ptr [rsp+0B0h+phkResult], 3; unsigned int
0x1800126eb  lea     r9, [rbp+57h+var_80]; unsigned int *
0x1800126ef  lea     r8, [rbp+57h+var_78]; unsigned __int8 **
0x1800126f3  lea     rdx, aSslcertificate; "SSLCertificateSHA1Hash"
0x1800126fa  mov     rcx, rdi; this
0x1800126fd  call    ?ReadReg@CRegistry@@QEAAKPEBGPEAPEAEPEAKK@Z; CRegistry::ReadReg(ushort const *,uchar * *,ulong *,ulong)
0x180012702  mov     ebx, eax
0x180012704  test    eax, eax
0x180012706  jle     short loc_180012711
0x180012708  movzx   ebx, ax
0x18001270b  or      ebx, 80070000h
0x180012711  test    ebx, ebx
0x180012713  jns     short loc_18001277E
0x180012715  lea     rdx, aPregReadregbin; "pReg->ReadRegBinary failed: 0x%x in %s"
0x18001271c  jmp     short loc_180012768
0x18001271e  lea     rdi, [rbp+57h+var_70]
0x180012722  lea     rax, [rbp+57h+hKey]
0x180012726  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18001272b  mov     r9d, 20019h; samDesired
0x180012731  xor     r8d, r8d; ulOptions
0x180012734  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Control\\Ter"...
0x18001273b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012742  call    cs:__imp_RegOpenKeyExW
0x180012748  mov     ebx, eax
0x18001274a  test    eax, eax
0x18001274c  jz      short loc_18001275D
0x18001274e  mov     [rbp+57h+hKey], r15
0x180012752  jle     short loc_18001275D
0x180012754  movzx   ebx, ax
0x180012757  or      ebx, 80070000h
0x18001275d  test    ebx, ebx
0x18001275f  jns     short loc_1800126E3
0x180012761  lea     rdx, aPregOpenkeyFai; "pReg->OpenKey failed: 0x%x in %s"
0x180012768  mov     r8d, ebx
0x18001276b  lea     r9, aCcertmanagerGe_0; "CCertManager::GetHashFromTheRegistry"
0x180012772  mov     ecx, 8; int
0x180012777  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001277c  jmp     short loc_1800127B7
0x18001277e  cmp     [rbp+57h+var_80], 14h
0x180012782  jz      short loc_18001278B
0x180012784  mov     ebx, 8007000Dh
0x180012789  jmp     short loc_1800127B7
0x18001278b  mov     ecx, r15d
0x18001278e  mov     rdx, [rbp+57h+var_78]
0x180012792  cmp     ecx, 14h
0x180012795  jnb     short loc_1800127B2
0x180012797  mov     eax, ecx
0x180012799  cmp     [rax+rdx], r15b
0x18001279d  jnz     short loc_1800127A3
0x18001279f  inc     ecx
0x1800127a1  jmp     short loc_180012792
0x1800127a3  movups  xmm0, xmmword ptr [rdx]
0x1800127a6  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x1800127aa  mov     eax, [rdx+10h]
0x1800127ad  mov     [rbp+57h+var_38], eax
0x1800127b0  jmp     short loc_1800127B7
0x1800127b2  mov     ebx, 80070002h
0x1800127b7  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x1800127be  mov     [rbp+57h+var_70], rax
0x1800127c2  mov     rcx, [rbp+57h+hKey]; hKey
0x1800127c6  test    rcx, rcx
0x1800127c9  jz      short loc_1800127D5
0x1800127cb  call    cs:__imp_RegCloseKey
0x1800127d1  mov     [rbp+57h+hKey], r15
0x1800127d5  mov     rcx, [rbp+57h+Block]; Block
0x1800127d9  test    rcx, rcx
0x1800127dc  jz      short loc_1800127E3
0x1800127de  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800127e3  cmp     ebx, 80070002h
0x1800127e9  jnz     short loc_1800127F3
0x1800127eb  mov     ebx, r15d
0x1800127ee  jmp     loc_180012879
0x1800127f3  cmp     ebx, 8007000Dh
0x1800127f9  jnz     short loc_180012825
0x1800127fb  xor     r9d, r9d; struct _CERT_CONTEXT *
0x1800127fe  mov     r8d, 0C0000423h; unsigned int
0x180012804  mov     rcx, r14; this
0x180012807  call    ?SecLogEvent@CCertManager@@AEAAJGIPEBU_CERT_CONTEXT@@@Z; CCertManager::SecLogEvent(ushort,uint,_CERT_CONTEXT const *)
0x18001280c  mov     dword ptr [rsp+0B0h+phkResult], r15d; unsigned int
0x180012811  xor     r9d, r9d; unsigned __int8 *
0x180012814  lea     r8, aSslcertificate; "SSLCertificateSHA1Hash"
0x18001281b  mov     rdx, rsi; struct CRegistry *
0x18001281e  call    ?PutHashInTheRegistry@CCertManager@@AEAAJPEAVCRegistry@@PEBGPEAEK@Z; CCertManager::PutHashInTheRegistry(CRegistry *,ushort const *,uchar *,ulong)
0x180012823  jmp     short loc_180012829
0x180012825  test    ebx, ebx
0x180012827  jns     short loc_180012846
0x180012829  lea     r9, aCcertmanagerUp_1; "CCertManager::UpdateCustomCertificate"
0x180012830  mov     r8d, ebx
0x180012833  lea     rdx, aGethashfromthe_0; "GetHashFromTheRegistry failed: 0x%x in "...
0x18001283a  mov     ecx, 8; int
0x18001283f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012844  jmp     short loc_180012879
0x180012846  lea     r9, [rbp+57h+var_7C]; int *
0x18001284a  lea     rdx, [rbp+57h+var_48]; unsigned __int8 *
0x18001284e  mov     rcx, r14; this
0x180012851  call    ?ValidateCertAndLogProblems@CCertManager@@AEAAJPEAEKPEAH@Z; CCertManager::ValidateCertAndLogProblems(uchar *,ulong,int *)
0x180012856  mov     ebx, eax
0x180012858  test    eax, eax
0x18001285a  jns     short loc_180012879
0x18001285c  cmp     [rbp+57h+var_7C], r15d
0x180012860  jnz     short loc_180012879
0x180012862  mov     dword ptr [rsp+0B0h+phkResult], r15d; unsigned int
0x180012867  xor     r9d, r9d; unsigned __int8 *
0x18001286a  lea     r8, aSslcertificate; "SSLCertificateSHA1Hash"
0x180012871  mov     rdx, rsi; struct CRegistry *
0x180012874  call    ?PutHashInTheRegistry@CCertManager@@AEAAJPEAVCRegistry@@PEBGPEAEK@Z; CCertManager::PutHashInTheRegistry(CRegistry *,ushort const *,uchar *,ulong)
0x180012879  mov     eax, ebx
0x18001287b  mov     rcx, [rbp+57h+var_30]
0x18001287f  xor     rcx, rsp; StackCookie
0x180012882  call    __security_check_cookie
0x180012887  mov     rbx, [rsp+0B0h+arg_10]
0x18001288f  add     rsp, 90h
0x180012896  pop     r15
0x180012898  pop     r14
0x18001289a  pop     rdi
0x18001289b  pop     rsi
0x18001289c  pop     rbp
0x18001289d  retn
```
