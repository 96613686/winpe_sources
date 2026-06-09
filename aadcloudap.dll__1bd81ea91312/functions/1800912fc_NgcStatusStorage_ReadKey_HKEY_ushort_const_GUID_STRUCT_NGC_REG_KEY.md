# NgcStatusStorage::ReadKey(HKEY__ *,ushort const *,_GUID,STRUCT_NGC_REG_KEY *)

- ea: `0x1800912fc`
- end: `0x180091567`
- name: `?ReadKey@NgcStatusStorage@@CAKPEAUHKEY__@@PEBGU_GUID@@PEAUSTRUCT_NGC_REG_KEY@@@Z`
- size: `619`
- prototype: `static unsigned int(HKEY, const unsigned __int16 *, struct _GUID *__struct_ptr, struct STRUCT_NGC_REG_KEY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180090ed0`

## callees

- `0x180086a54`
- `0x180086cdc`
- `0x1800871b4`
- `0x18008aa28`
- `0x18008aa64`
- `0x18008afb0`
- `0x1800912fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009134d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009134d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009150b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009150b`

## string_xrefs

- `0x1800913b8`: `RegReadDwordValue`
- `0x180091462`: `RegReadStringValue`
- `0x18009135c`: `RegOpenKeyExW`
- `0x180091377`: `%s: Cannot open NGC key registry. Key name: %s. Error code: 0x%08x.`
- `0x18009136d`: `NgcStatusStorage::ReadKey`
- `0x1800913c2`: `NgcStatusStorage::ReadKey`

## pseudocode

```c
__int64 __fastcall NgcStatusStorage::ReadKey(
        HKEY a1,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        struct STRUCT_NGC_REG_KEY *a4)
{
  unsigned __int16 **v4; // r14
  unsigned __int16 **v5; // r15
  unsigned __int16 **v6; // r12
  unsigned __int16 **v7; // r13
  struct STRUCT_NGC_REG_KEY *v8; // rdi
  LSTATUS v11; // eax
  unsigned int v12; // ebx
  unsigned int DwordValue; // eax
  const wchar_t *v14; // r8
  __int64 v15; // rax
  HKEY hKey; // [rsp+98h] [rbp+20h] BYREF

  v4 = (unsigned __int16 **)((char *)a4 + 16);
  v5 = (unsigned __int16 **)((char *)a4 + 40);
  hKey = 0;
  v6 = (unsigned __int16 **)((char *)a4 + 48);
  *((_QWORD *)a4 + 2) = 0;
  v7 = (unsigned __int16 **)((char *)a4 + 56);
  *((_QWORD *)a4 + 5) = 0;
  *((_QWORD *)a4 + 6) = 0;
  v8 = a4;
  *((_QWORD *)a4 + 7) = 0;
  v11 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  v12 = v11;
  if ( v11 )
  {
    Logger::WriteRegistryFailureEvent(v11, L"RegOpenKeyExW", a2);
    Logger::TraceInformation(
      L"%s: Cannot open NGC key registry. Key name: %s. Error code: 0x%08x.",
      L"NgcStatusStorage::ReadKey",
      a2,
      v12);
    goto LABEL_14;
  }
  DwordValue = RegReadDwordValue(hKey, 0, L"AttestationLevel", a2, (unsigned int *)v8 + 6, 0);
  v12 = DwordValue;
  if ( DwordValue
    || (DwordValue = RegReadDwordValue(hKey, 0, L"AikCertStatus", a2, (unsigned int *)v8 + 7, 0), (v12 = DwordValue) != 0)
    || (DwordValue = RegReadDwordValue(hKey, 0, L"NgcKeyStatus", a2, (unsigned int *)v8 + 8, 0), (v12 = DwordValue) != 0) )
  {
    v14 = L"RegReadDwordValue";
LABEL_5:
    Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", L"NgcStatusStorage::ReadKey", v14, DwordValue);
    goto LABEL_14;
  }
  DwordValue = RegReadStringValue(hKey, 0, L"NgcKeyName", a2, 2u, v4);
  v12 = DwordValue;
  if ( DwordValue
    || (DwordValue = RegReadStringValue(hKey, 0, L"IdpDomain", a2, 2u, v5), (v12 = DwordValue) != 0)
    || (DwordValue = RegReadStringValue(hKey, 0, L"TenantDomain", a2, 2u, v6), (v12 = DwordValue) != 0)
    || (DwordValue = RegReadStringValue(hKey, 0, L"UserId", a2, 2u, v7), (v12 = DwordValue) != 0) )
  {
    v14 = L"RegReadStringValue";
    goto LABEL_5;
  }
  *(struct _GUID *)v8 = *a3;
LABEL_14:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v12 )
  {
    SafeFree(*v4);
    SafeFree(*v5);
    SafeFree(*v6);
    SafeFree(*v7);
    v15 = 64;
    do
    {
      *(_BYTE *)v8 = 0;
      v8 = (struct STRUCT_NGC_REG_KEY *)((char *)v8 + 1);
      --v15;
    }
    while ( v15 );
  }
  return v12;
}

```

## disassembly

```asm
0x1800912fc  mov     r11, rsp
0x1800912ff  push    rbx
0x180091300  push    rbp
0x180091301  push    rsi
0x180091302  push    rdi
0x180091303  push    r12
0x180091305  push    r13
0x180091307  push    r14
0x180091309  push    r15
0x18009130b  sub     rsp, 38h
0x18009130f  xor     eax, eax
0x180091311  lea     r14, [r9+10h]
0x180091315  lea     r15, [r9+28h]
0x180091319  mov     [r11+20h], rax
0x18009131d  lea     r12, [r9+30h]
0x180091321  mov     [r14], rax
0x180091324  lea     r13, [r9+38h]
0x180091328  mov     [r15], rax
0x18009132b  mov     [r12], rax
0x18009132f  mov     rdi, r9
0x180091332  mov     [r13+0], rax
0x180091336  mov     rbp, r8
0x180091339  lea     rax, [r11+20h]
0x18009133d  mov     r9d, 20019h; samDesired
0x180091343  xor     r8d, r8d; ulOptions
0x180091346  mov     [r11-58h], rax
0x18009134a  mov     rsi, rdx
0x18009134d  call    cs:__imp_RegOpenKeyExW
0x180091353  mov     ebx, eax
0x180091355  test    eax, eax
0x180091357  jz      short loc_180091388
0x180091359  mov     r8, rsi; unsigned __int16 *
0x18009135c  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180091363  mov     ecx, eax; unsigned int
0x180091365  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x18009136a  mov     r9d, ebx
0x18009136d  lea     rdx, aNgcstatusstora_0; "NgcStatusStorage::ReadKey"
0x180091374  mov     r8, rsi
0x180091377  lea     rcx, aSCannotOpenNgc; "%s: Cannot open NGC key registry. Key n"...
0x18009137e  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180091383  jmp     loc_1800914FE
0x180091388  mov     rcx, [rsp+78h+hKey]; HKEY
0x180091390  lea     rax, [rdi+18h]
0x180091394  mov     dword ptr [rsp+78h+var_50], 0; unsigned int
0x18009139c  lea     r8, aAttestationlev; "AttestationLevel"
0x1800913a3  mov     r9, rsi; unsigned __int16 *
0x1800913a6  mov     qword ptr [rsp+78h+dwFlags], rax; unsigned int *
0x1800913ab  xor     edx, edx; unsigned __int16 *
0x1800913ad  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x1800913b2  mov     ebx, eax
0x1800913b4  test    eax, eax
0x1800913b6  jz      short loc_1800913DA
0x1800913b8  lea     r8, aRegreaddwordva; "RegReadDwordValue"
0x1800913bf  mov     r9d, eax
0x1800913c2  lea     rdx, aNgcstatusstora_0; "NgcStatusStorage::ReadKey"
0x1800913c9  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x1800913d0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800913d5  jmp     loc_1800914FE
0x1800913da  mov     rcx, [rsp+78h+hKey]; HKEY
0x1800913e2  lea     rax, [rdi+1Ch]
0x1800913e6  mov     dword ptr [rsp+78h+var_50], 0; unsigned int
0x1800913ee  lea     r8, aAikcertstatus; "AikCertStatus"
0x1800913f5  mov     r9, rsi; unsigned __int16 *
0x1800913f8  mov     qword ptr [rsp+78h+dwFlags], rax; unsigned int *
0x1800913fd  xor     edx, edx; unsigned __int16 *
0x1800913ff  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x180091404  mov     ebx, eax
0x180091406  test    eax, eax
0x180091408  jnz     short loc_1800913B8
0x18009140a  mov     rcx, [rsp+78h+hKey]; HKEY
0x180091412  lea     rax, [rdi+20h]
0x180091416  mov     dword ptr [rsp+78h+var_50], ebx; unsigned int
0x18009141a  lea     r8, aNgckeystatus; "NgcKeyStatus"
0x180091421  mov     r9, rsi; unsigned __int16 *
0x180091424  mov     qword ptr [rsp+78h+dwFlags], rax; unsigned int *
0x180091429  xor     edx, edx; unsigned __int16 *
0x18009142b  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x180091430  mov     ebx, eax
0x180091432  test    eax, eax
0x180091434  jnz     short loc_1800913B8
0x180091436  mov     rcx, [rsp+78h+hKey]; hkey
0x18009143e  lea     r8, aNgckeyname; "NgcKeyName"
0x180091445  mov     [rsp+78h+var_50], r14; unsigned __int16 **
0x18009144a  mov     r9, rsi; unsigned __int16 *
0x18009144d  xor     edx, edx; lpSubKey
0x18009144f  mov     [rsp+78h+dwFlags], 2; dwFlags
0x180091457  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18009145c  mov     ebx, eax
0x18009145e  test    eax, eax
0x180091460  jz      short loc_18009146E
0x180091462  lea     r8, aRegreadstringv; "RegReadStringValue"
0x180091469  jmp     loc_1800913BF
0x18009146e  mov     rcx, [rsp+78h+hKey]; hkey
0x180091476  lea     r8, aIdpdomain; "IdpDomain"
0x18009147d  mov     [rsp+78h+var_50], r15; unsigned __int16 **
0x180091482  mov     r9, rsi; unsigned __int16 *
0x180091485  xor     edx, edx; lpSubKey
0x180091487  mov     [rsp+78h+dwFlags], 2; dwFlags
0x18009148f  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x180091494  mov     ebx, eax
0x180091496  test    eax, eax
0x180091498  jnz     short loc_180091462
0x18009149a  mov     rcx, [rsp+78h+hKey]; hkey
0x1800914a2  lea     r8, aTenantdomain; "TenantDomain"
0x1800914a9  mov     [rsp+78h+var_50], r12; unsigned __int16 **
0x1800914ae  mov     r9, rsi; unsigned __int16 *
0x1800914b1  xor     edx, edx; lpSubKey
0x1800914b3  mov     [rsp+78h+dwFlags], 2; dwFlags
0x1800914bb  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x1800914c0  mov     ebx, eax
0x1800914c2  test    eax, eax
0x1800914c4  jnz     short loc_180091462
0x1800914c6  mov     rcx, [rsp+78h+hKey]; hkey
0x1800914ce  lea     r8, aUserid; "UserId"
0x1800914d5  mov     [rsp+78h+var_50], r13; unsigned __int16 **
0x1800914da  mov     r9, rsi; unsigned __int16 *
0x1800914dd  xor     edx, edx; lpSubKey
0x1800914df  mov     [rsp+78h+dwFlags], 2; dwFlags
0x1800914e7  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x1800914ec  mov     ebx, eax
0x1800914ee  test    eax, eax
0x1800914f0  jnz     loc_180091462
0x1800914f6  movaps  xmm0, xmmword ptr [rbp+0]
0x1800914fa  movdqu  xmmword ptr [rdi], xmm0
0x1800914fe  mov     rcx, [rsp+78h+hKey]; hKey
0x180091506  test    rcx, rcx
0x180091509  jz      short loc_18009151D
0x18009150b  call    cs:__imp_RegCloseKey
0x180091511  mov     [rsp+78h+hKey], 0
0x18009151d  test    ebx, ebx
0x18009151f  jz      short loc_180091554
0x180091521  mov     rcx, [r14]; void *
0x180091524  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180091529  mov     rcx, [r15]; void *
0x18009152c  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180091531  mov     rcx, [r12]; void *
0x180091535  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18009153a  mov     rcx, [r13+0]; void *
0x18009153e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180091543  mov     eax, 40h ; '@'
0x180091548  mov     byte ptr [rdi], 0
0x18009154b  inc     rdi
0x18009154e  sub     rax, 1
0x180091552  jnz     short loc_180091548
0x180091554  mov     eax, ebx
0x180091556  add     rsp, 38h
0x18009155a  pop     r15
0x18009155c  pop     r14
0x18009155e  pop     r13
0x180091560  pop     r12
0x180091562  pop     rdi
0x180091563  pop     rsi
0x180091564  pop     rbp
0x180091565  pop     rbx
0x180091566  retn
```
