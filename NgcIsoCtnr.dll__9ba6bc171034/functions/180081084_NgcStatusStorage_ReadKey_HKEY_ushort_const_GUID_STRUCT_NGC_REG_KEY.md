# NgcStatusStorage::ReadKey(HKEY__ *,ushort const *,_GUID,STRUCT_NGC_REG_KEY *)

- ea: `0x180081084`
- end: `0x1800812b7`
- name: `?ReadKey@NgcStatusStorage@@CAKPEAUHKEY__@@PEBGU_GUID@@PEAUSTRUCT_NGC_REG_KEY@@@Z`
- size: `563`
- prototype: `static unsigned int(HKEY, const unsigned __int16 *, struct _GUID *__struct_ptr, struct STRUCT_NGC_REG_KEY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180080c58`

## callees

- `0x1800798a0`
- `0x180079b18`
- `0x180079de0`
- `0x18007d1b8`
- `0x18007d1f4`
- `0x18007d37c`
- `0x180081084`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800810d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800810d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008125b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008125b`

## string_xrefs

- `0x180081138`: `RegReadDwordValue`
- `0x1800811ce`: `RegReadStringValue`
- `0x1800810e4`: `RegOpenKeyExW`
- `0x1800810f5`: `NgcStatusStorage::ReadKey`
- `0x180081142`: `NgcStatusStorage::ReadKey`
- `0x1800810ff`: `%s: Cannot open NGC key registry. Key name: %s. Error code: 0x%08x.`

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
  DWORD v17; // [rsp+20h] [rbp-58h]
  DWORD v18; // [rsp+20h] [rbp-58h]
  DWORD v19; // [rsp+20h] [rbp-58h]
  DWORD v20; // [rsp+20h] [rbp-58h]
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
  DwordValue = RegReadStringValue(hKey, 0, L"NgcKeyName", a2, v17, v4);
  v12 = DwordValue;
  if ( DwordValue
    || (DwordValue = RegReadStringValue(hKey, 0, L"IdpDomain", a2, v18, v5), (v12 = DwordValue) != 0)
    || (DwordValue = RegReadStringValue(hKey, 0, L"TenantDomain", a2, v19, v6), (v12 = DwordValue) != 0)
    || (DwordValue = RegReadStringValue(hKey, 0, L"UserId", a2, v20, v7), (v12 = DwordValue) != 0) )
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
0x180081084  mov     r11, rsp
0x180081087  push    rbx
0x180081088  push    rbp
0x180081089  push    rsi
0x18008108a  push    rdi
0x18008108b  push    r12
0x18008108d  push    r13
0x18008108f  push    r14
0x180081091  push    r15
0x180081093  sub     rsp, 38h
0x180081097  xor     eax, eax
0x180081099  lea     r14, [r9+10h]
0x18008109d  lea     r15, [r9+28h]
0x1800810a1  mov     [r11+20h], rax
0x1800810a5  lea     r12, [r9+30h]
0x1800810a9  mov     [r14], rax
0x1800810ac  lea     r13, [r9+38h]
0x1800810b0  mov     [r15], rax
0x1800810b3  mov     [r12], rax
0x1800810b7  mov     rdi, r9
0x1800810ba  mov     [r13+0], rax
0x1800810be  mov     rbp, r8
0x1800810c1  lea     rax, [r11+20h]
0x1800810c5  mov     r9d, 20019h; samDesired
0x1800810cb  xor     r8d, r8d; ulOptions
0x1800810ce  mov     [r11-58h], rax
0x1800810d2  mov     rsi, rdx
0x1800810d5  call    cs:__imp_RegOpenKeyExW
0x1800810db  mov     ebx, eax
0x1800810dd  test    eax, eax
0x1800810df  jz      short loc_180081110
0x1800810e1  mov     r8, rsi; unsigned __int16 *
0x1800810e4  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800810eb  mov     ecx, eax; unsigned int
0x1800810ed  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x1800810f2  mov     r9d, ebx
0x1800810f5  lea     rdx, aNgcstatusstora_0; "NgcStatusStorage::ReadKey"
0x1800810fc  mov     r8, rsi
0x1800810ff  lea     rcx, aSCannotOpenNgc; "%s: Cannot open NGC key registry. Key n"...
0x180081106  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18008110b  jmp     loc_18008124E
0x180081110  mov     rcx, [rsp+78h+hKey]; HKEY
0x180081118  lea     rax, [rdi+18h]
0x18008111c  mov     r9, rsi; unsigned __int16 *
0x18008111f  mov     qword ptr [rsp+78h+var_58], rax; unsigned int *
0x180081124  lea     r8, aAttestationlev; "AttestationLevel"
0x18008112b  xor     edx, edx; unsigned __int16 *
0x18008112d  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x180081132  mov     ebx, eax
0x180081134  test    eax, eax
0x180081136  jz      short loc_18008115A
0x180081138  lea     r8, aRegreaddwordva; "RegReadDwordValue"
0x18008113f  mov     r9d, eax
0x180081142  lea     rdx, aNgcstatusstora_0; "NgcStatusStorage::ReadKey"
0x180081149  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180081150  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180081155  jmp     loc_18008124E
0x18008115a  mov     rcx, [rsp+78h+hKey]; HKEY
0x180081162  lea     rax, [rdi+1Ch]
0x180081166  mov     r9, rsi; unsigned __int16 *
0x180081169  mov     qword ptr [rsp+78h+var_58], rax; unsigned int *
0x18008116e  lea     r8, aAikcertstatus; "AikCertStatus"
0x180081175  xor     edx, edx; unsigned __int16 *
0x180081177  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x18008117c  mov     ebx, eax
0x18008117e  test    eax, eax
0x180081180  jnz     short loc_180081138
0x180081182  mov     rcx, [rsp+78h+hKey]; HKEY
0x18008118a  lea     rax, [rdi+20h]
0x18008118e  mov     r9, rsi; unsigned __int16 *
0x180081191  mov     qword ptr [rsp+78h+var_58], rax; DWORD
0x180081196  lea     r8, aNgckeystatus; "NgcKeyStatus"
0x18008119d  xor     edx, edx; unsigned __int16 *
0x18008119f  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x1800811a4  mov     ebx, eax
0x1800811a6  test    eax, eax
0x1800811a8  jnz     short loc_180081138
0x1800811aa  mov     rcx, [rsp+78h+hKey]; hkey
0x1800811b2  lea     r8, aNgckeyname; "NgcKeyName"
0x1800811b9  mov     r9, rsi; unsigned __int16 *
0x1800811bc  mov     qword ptr [rsp+78h+var_50], r14; unsigned __int16 **
0x1800811c1  xor     edx, edx; lpSubKey
0x1800811c3  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x1800811c8  mov     ebx, eax
0x1800811ca  test    eax, eax
0x1800811cc  jz      short loc_1800811DA
0x1800811ce  lea     r8, aRegreadstringv; "RegReadStringValue"
0x1800811d5  jmp     loc_18008113F
0x1800811da  mov     rcx, [rsp+78h+hKey]; hkey
0x1800811e2  lea     r8, aIdpdomain; "IdpDomain"
0x1800811e9  mov     r9, rsi; unsigned __int16 *
0x1800811ec  mov     qword ptr [rsp+78h+var_50], r15; unsigned __int16 **
0x1800811f1  xor     edx, edx; lpSubKey
0x1800811f3  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x1800811f8  mov     ebx, eax
0x1800811fa  test    eax, eax
0x1800811fc  jnz     short loc_1800811CE
0x1800811fe  mov     rcx, [rsp+78h+hKey]; hkey
0x180081206  lea     r8, aTenantdomain; "TenantDomain"
0x18008120d  mov     r9, rsi; unsigned __int16 *
0x180081210  mov     qword ptr [rsp+78h+var_50], r12; unsigned __int16 **
0x180081215  xor     edx, edx; lpSubKey
0x180081217  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18008121c  mov     ebx, eax
0x18008121e  test    eax, eax
0x180081220  jnz     short loc_1800811CE
0x180081222  mov     rcx, [rsp+78h+hKey]; hkey
0x18008122a  lea     r8, aUserid; "UserId"
0x180081231  mov     r9, rsi; unsigned __int16 *
0x180081234  mov     qword ptr [rsp+78h+var_50], r13; unsigned __int16 **
0x180081239  xor     edx, edx; lpSubKey
0x18008123b  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x180081240  mov     ebx, eax
0x180081242  test    eax, eax
0x180081244  jnz     short loc_1800811CE
0x180081246  movaps  xmm0, xmmword ptr [rbp+0]
0x18008124a  movdqu  xmmword ptr [rdi], xmm0
0x18008124e  mov     rcx, [rsp+78h+hKey]; hKey
0x180081256  test    rcx, rcx
0x180081259  jz      short loc_18008126D
0x18008125b  call    cs:__imp_RegCloseKey
0x180081261  mov     [rsp+78h+hKey], 0
0x18008126d  test    ebx, ebx
0x18008126f  jz      short loc_1800812A4
0x180081271  mov     rcx, [r14]; void *
0x180081274  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180081279  mov     rcx, [r15]; void *
0x18008127c  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180081281  mov     rcx, [r12]; void *
0x180081285  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008128a  mov     rcx, [r13+0]; void *
0x18008128e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180081293  mov     eax, 40h ; '@'
0x180081298  mov     byte ptr [rdi], 0
0x18008129b  inc     rdi
0x18008129e  sub     rax, 1
0x1800812a2  jnz     short loc_180081298
0x1800812a4  mov     eax, ebx
0x1800812a6  add     rsp, 38h
0x1800812aa  pop     r15
0x1800812ac  pop     r14
0x1800812ae  pop     r13
0x1800812b0  pop     r12
0x1800812b2  pop     rdi
0x1800812b3  pop     rsi
0x1800812b4  pop     rbp
0x1800812b5  pop     rbx
0x1800812b6  retn
```
