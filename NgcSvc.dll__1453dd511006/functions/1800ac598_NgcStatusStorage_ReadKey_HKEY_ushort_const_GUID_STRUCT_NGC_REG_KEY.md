# NgcStatusStorage::ReadKey(HKEY__ *,ushort const *,_GUID,STRUCT_NGC_REG_KEY *)

- ea: `0x1800ac598`
- end: `0x1800ac7cb`
- name: `?ReadKey@NgcStatusStorage@@CAKPEAUHKEY__@@PEBGU_GUID@@PEAUSTRUCT_NGC_REG_KEY@@@Z`
- size: `563`
- prototype: `static unsigned int(HKEY, const unsigned __int16 *, struct _GUID *__struct_ptr, struct STRUCT_NGC_REG_KEY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180020df8`

## callees

- `0x1800215e4`
- `0x18002a0b0`
- `0x18002f2d0`
- `0x18004a650`
- `0x18004aa08`
- `0x18004d820`
- `0x1800ac598`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ac5e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ac5e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ac76f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ac76f`

## string_xrefs

- `0x1800ac6e2`: `RegReadStringValue`
- `0x1800ac64c`: `RegReadDwordValue`
- `0x1800ac5f8`: `RegOpenKeyExW`
- `0x1800ac613`: `%s: Cannot open NGC key registry. Key name: %s. Error code: 0x%08x.`
- `0x1800ac609`: `NgcStatusStorage::ReadKey`
- `0x1800ac656`: `NgcStatusStorage::ReadKey`

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
  SIZE_T dwBytes; // [rsp+20h] [rbp-58h]
  SIZE_T dwBytesa; // [rsp+20h] [rbp-58h]
  SIZE_T dwBytesb; // [rsp+20h] [rbp-58h]
  SIZE_T dwBytesc; // [rsp+20h] [rbp-58h]
  unsigned int v21; // [rsp+28h] [rbp-50h]
  unsigned int v22; // [rsp+28h] [rbp-50h]
  unsigned int v23; // [rsp+28h] [rbp-50h]
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
  DwordValue = RegReadDwordValue(hKey, 0, L"AttestationLevel", a2, (unsigned int *)v8 + 6, v21);
  v12 = DwordValue;
  if ( DwordValue
    || (DwordValue = RegReadDwordValue(hKey, 0, L"AikCertStatus", a2, (unsigned int *)v8 + 7, v22),
        (v12 = DwordValue) != 0)
    || (DwordValue = RegReadDwordValue(hKey, 0, L"NgcKeyStatus", a2, (unsigned int *)v8 + 8, v23),
        (v12 = DwordValue) != 0) )
  {
    v14 = L"RegReadDwordValue";
LABEL_5:
    Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", L"NgcStatusStorage::ReadKey", v14, DwordValue);
    goto LABEL_14;
  }
  DwordValue = RegReadStringValue(hKey, 0, L"NgcKeyName", a2, dwBytes, v4);
  v12 = DwordValue;
  if ( DwordValue
    || (DwordValue = RegReadStringValue(hKey, 0, L"IdpDomain", a2, dwBytesa, v5), (v12 = DwordValue) != 0)
    || (DwordValue = RegReadStringValue(hKey, 0, L"TenantDomain", a2, dwBytesb, v6), (v12 = DwordValue) != 0)
    || (DwordValue = RegReadStringValue(hKey, 0, L"UserId", a2, dwBytesc, v7), (v12 = DwordValue) != 0) )
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
0x1800ac598  mov     r11, rsp
0x1800ac59b  push    rbx
0x1800ac59c  push    rbp
0x1800ac59d  push    rsi
0x1800ac59e  push    rdi
0x1800ac59f  push    r12
0x1800ac5a1  push    r13
0x1800ac5a3  push    r14
0x1800ac5a5  push    r15
0x1800ac5a7  sub     rsp, 38h
0x1800ac5ab  xor     eax, eax
0x1800ac5ad  lea     r14, [r9+10h]
0x1800ac5b1  lea     r15, [r9+28h]
0x1800ac5b5  mov     [r11+20h], rax
0x1800ac5b9  lea     r12, [r9+30h]
0x1800ac5bd  mov     [r14], rax
0x1800ac5c0  lea     r13, [r9+38h]
0x1800ac5c4  mov     [r15], rax
0x1800ac5c7  mov     [r12], rax
0x1800ac5cb  mov     rdi, r9
0x1800ac5ce  mov     [r13+0], rax
0x1800ac5d2  mov     rbp, r8
0x1800ac5d5  lea     rax, [r11+20h]
0x1800ac5d9  mov     r9d, 20019h; samDesired
0x1800ac5df  xor     r8d, r8d; ulOptions
0x1800ac5e2  mov     [r11-58h], rax
0x1800ac5e6  mov     rsi, rdx
0x1800ac5e9  call    cs:__imp_RegOpenKeyExW
0x1800ac5ef  mov     ebx, eax
0x1800ac5f1  test    eax, eax
0x1800ac5f3  jz      short loc_1800AC624
0x1800ac5f5  mov     r8, rsi; unsigned __int16 *
0x1800ac5f8  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800ac5ff  mov     ecx, eax; unsigned int
0x1800ac601  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x1800ac606  mov     r9d, ebx
0x1800ac609  lea     rdx, aNgcstatusstora_0; "NgcStatusStorage::ReadKey"
0x1800ac610  mov     r8, rsi
0x1800ac613  lea     rcx, aSCannotOpenNgc; "%s: Cannot open NGC key registry. Key n"...
0x1800ac61a  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800ac61f  jmp     loc_1800AC762
0x1800ac624  mov     rcx, [rsp+78h+hKey]; HKEY
0x1800ac62c  lea     rax, [rdi+18h]
0x1800ac630  mov     r9, rsi; unsigned __int16 *
0x1800ac633  mov     [rsp+78h+dwBytes], rax; unsigned int *
0x1800ac638  lea     r8, aAttestationlev; "AttestationLevel"
0x1800ac63f  xor     edx, edx; unsigned __int16 *
0x1800ac641  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x1800ac646  mov     ebx, eax
0x1800ac648  test    eax, eax
0x1800ac64a  jz      short loc_1800AC66E
0x1800ac64c  lea     r8, aRegreaddwordva; "RegReadDwordValue"
0x1800ac653  mov     r9d, eax
0x1800ac656  lea     rdx, aNgcstatusstora_0; "NgcStatusStorage::ReadKey"
0x1800ac65d  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x1800ac664  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ac669  jmp     loc_1800AC762
0x1800ac66e  mov     rcx, [rsp+78h+hKey]; HKEY
0x1800ac676  lea     rax, [rdi+1Ch]
0x1800ac67a  mov     r9, rsi; unsigned __int16 *
0x1800ac67d  mov     [rsp+78h+dwBytes], rax; unsigned int *
0x1800ac682  lea     r8, aAikcertstatus; "AikCertStatus"
0x1800ac689  xor     edx, edx; unsigned __int16 *
0x1800ac68b  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x1800ac690  mov     ebx, eax
0x1800ac692  test    eax, eax
0x1800ac694  jnz     short loc_1800AC64C
0x1800ac696  mov     rcx, [rsp+78h+hKey]; HKEY
0x1800ac69e  lea     rax, [rdi+20h]
0x1800ac6a2  mov     r9, rsi; unsigned __int16 *
0x1800ac6a5  mov     [rsp+78h+dwBytes], rax; dwBytes
0x1800ac6aa  lea     r8, aNgckeystatus; "NgcKeyStatus"
0x1800ac6b1  xor     edx, edx; unsigned __int16 *
0x1800ac6b3  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x1800ac6b8  mov     ebx, eax
0x1800ac6ba  test    eax, eax
0x1800ac6bc  jnz     short loc_1800AC64C
0x1800ac6be  mov     rcx, [rsp+78h+hKey]; hkey
0x1800ac6c6  lea     r8, aNgckeyname; "NgcKeyName"
0x1800ac6cd  mov     r9, rsi; unsigned __int16 *
0x1800ac6d0  mov     qword ptr [rsp+78h+var_50], r14; unsigned __int16 **
0x1800ac6d5  xor     edx, edx; lpSubKey
0x1800ac6d7  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x1800ac6dc  mov     ebx, eax
0x1800ac6de  test    eax, eax
0x1800ac6e0  jz      short loc_1800AC6EE
0x1800ac6e2  lea     r8, aRegreadstringv; "RegReadStringValue"
0x1800ac6e9  jmp     loc_1800AC653
0x1800ac6ee  mov     rcx, [rsp+78h+hKey]; hkey
0x1800ac6f6  lea     r8, aIdpdomain; "IdpDomain"
0x1800ac6fd  mov     r9, rsi; unsigned __int16 *
0x1800ac700  mov     qword ptr [rsp+78h+var_50], r15; unsigned __int16 **
0x1800ac705  xor     edx, edx; lpSubKey
0x1800ac707  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x1800ac70c  mov     ebx, eax
0x1800ac70e  test    eax, eax
0x1800ac710  jnz     short loc_1800AC6E2
0x1800ac712  mov     rcx, [rsp+78h+hKey]; hkey
0x1800ac71a  lea     r8, aTenantdomain; "TenantDomain"
0x1800ac721  mov     r9, rsi; unsigned __int16 *
0x1800ac724  mov     qword ptr [rsp+78h+var_50], r12; unsigned __int16 **
0x1800ac729  xor     edx, edx; lpSubKey
0x1800ac72b  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x1800ac730  mov     ebx, eax
0x1800ac732  test    eax, eax
0x1800ac734  jnz     short loc_1800AC6E2
0x1800ac736  mov     rcx, [rsp+78h+hKey]; hkey
0x1800ac73e  lea     r8, aUserid; "UserId"
0x1800ac745  mov     r9, rsi; unsigned __int16 *
0x1800ac748  mov     qword ptr [rsp+78h+var_50], r13; unsigned __int16 **
0x1800ac74d  xor     edx, edx; lpSubKey
0x1800ac74f  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x1800ac754  mov     ebx, eax
0x1800ac756  test    eax, eax
0x1800ac758  jnz     short loc_1800AC6E2
0x1800ac75a  movaps  xmm0, xmmword ptr [rbp+0]
0x1800ac75e  movdqu  xmmword ptr [rdi], xmm0
0x1800ac762  mov     rcx, [rsp+78h+hKey]; hKey
0x1800ac76a  test    rcx, rcx
0x1800ac76d  jz      short loc_1800AC781
0x1800ac76f  call    cs:__imp_RegCloseKey
0x1800ac775  mov     [rsp+78h+hKey], 0
0x1800ac781  test    ebx, ebx
0x1800ac783  jz      short loc_1800AC7B8
0x1800ac785  mov     rcx, [r14]; void *
0x1800ac788  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800ac78d  mov     rcx, [r15]; void *
0x1800ac790  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800ac795  mov     rcx, [r12]; void *
0x1800ac799  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800ac79e  mov     rcx, [r13+0]; void *
0x1800ac7a2  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800ac7a7  mov     eax, 40h ; '@'
0x1800ac7ac  mov     byte ptr [rdi], 0
0x1800ac7af  inc     rdi
0x1800ac7b2  sub     rax, 1
0x1800ac7b6  jnz     short loc_1800AC7AC
0x1800ac7b8  mov     eax, ebx
0x1800ac7ba  add     rsp, 38h
0x1800ac7be  pop     r15
0x1800ac7c0  pop     r14
0x1800ac7c2  pop     r13
0x1800ac7c4  pop     r12
0x1800ac7c6  pop     rdi
0x1800ac7c7  pop     rsi
0x1800ac7c8  pop     rbp
0x1800ac7c9  pop     rbx
0x1800ac7ca  retn
```
