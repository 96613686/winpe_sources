# JoinStatusStorage::ReadDeviceKey(struct_join_status *,RegistryPath &,int)

- ea: `0x18008d02c`
- end: `0x18008d3fc`
- name: `?ReadDeviceKey@JoinStatusStorage@@CAJPEAUstruct_join_status@@AEAVRegistryPath@@H@Z`
- size: `976`
- prototype: `static int(struct struct_join_status *, struct RegistryPath *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18008d404`

## callees

- `0x1800871b4`
- `0x18008aa28`
- `0x18008d02c`
- `0x180092138`
- `0x180092364`
- `0x1800923dc`
- `0x180092444`

## string_xrefs

- `0x18008d05f`: `RegistryPath::OpenSubKey`
- `0x18008d186`: `RegistryPath::ReadDwordValue`
- `0x18008d1c3`: `RegistryPath::ReadDwordValue`
- `0x18008d200`: `RegistryPath::ReadDwordValue`
- `0x18008d321`: `RegistryPath::ReadDwordValue`
- `0x18008d398`: `RegistryPath::ReadQwordValue`
- `0x18008d052`: `JoinStatusStorage::ReadDeviceKey`
- `0x18008d0a0`: `JoinStatusStorage::ReadDeviceKey`
- `0x18008d0b7`: `RegistryPath::ReadStringValue`
- `0x18008d100`: `RegistryPath::ReadStringValue`
- `0x18008d149`: `RegistryPath::ReadStringValue`
- `0x18008d24c`: `RegistryPath::ReadStringValue`
- `0x18008d298`: `RegistryPath::ReadStringValue`
- `0x18008d2e4`: `RegistryPath::ReadStringValue`
- `0x18008d369`: `RegistryPath::ReadStringValue`
- `0x18008d3dc`: `%s: Failed to read one or more join status entries from the registry.`

## pseudocode

```c
__int64 __fastcall JoinStatusStorage::ReadDeviceKey(struct struct_join_status *a1, struct RegistryPath *a2, int a3)
{
  unsigned int v6; // eax
  int v7; // ebx
  _QWORD *v8; // rdi
  unsigned int StringValue; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int DwordValue; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  const unsigned __int16 *v20; // rdx
  __int64 v21; // r9
  unsigned int QwordValue; // eax

  v6 = RegistryPath::OpenSubKey(a2, (unsigned int)a2, a3);
  v7 = v6;
  if ( v6 )
  {
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadDeviceKey",
      L"RegistryPath::OpenSubKey",
      v6);
    v8 = (_QWORD *)((char *)a1 + 8);
  }
  else
  {
    v8 = (_QWORD *)((char *)a1 + 8);
    SafeFree(*((void **)a1 + 1));
    *((_QWORD *)a1 + 1) = 0;
    StringValue = RegistryPath::ReadStringValue(a2, L"IdpDomain", (unsigned __int16 **)a1 + 1);
    v7 = StringValue;
    if ( !StringValue
      || (Logger::TraceError(
            L"%s: %s failed with win32 error code: 0x%08x.",
            L"JoinStatusStorage::ReadDeviceKey",
            L"RegistryPath::ReadStringValue",
            StringValue),
          a3) )
    {
      SafeFree(*((void **)a1 + 2));
      *((_QWORD *)a1 + 2) = 0;
      v10 = RegistryPath::ReadStringValue(a2, L"TenantId", (unsigned __int16 **)a1 + 2);
      v7 = v10;
      if ( !v10
        || (Logger::TraceError(
              L"%s: %s failed with win32 error code: 0x%08x.",
              L"JoinStatusStorage::ReadDeviceKey",
              L"RegistryPath::ReadStringValue",
              v10),
            a3) )
      {
        SafeFree(*((void **)a1 + 3));
        *((_QWORD *)a1 + 3) = 0;
        v11 = RegistryPath::ReadStringValue(a2, L"UserEmail", (unsigned __int16 **)a1 + 3);
        v7 = v11;
        if ( !v11
          || (Logger::TraceError(
                L"%s: %s failed with win32 error code: 0x%08x.",
                L"JoinStatusStorage::ReadDeviceKey",
                L"RegistryPath::ReadStringValue",
                v11),
              a3) )
        {
          DwordValue = RegistryPath::ReadDwordValue(a2, L"TransportKeyStatus", (unsigned int *)a1 + 54, 0);
          v7 = DwordValue;
          if ( !DwordValue
            || (Logger::TraceError(
                  L"%s: %s failed with win32 error code: 0x%08x.",
                  L"JoinStatusStorage::ReadDeviceKey",
                  L"RegistryPath::ReadDwordValue",
                  DwordValue),
                a3) )
          {
            v13 = RegistryPath::ReadDwordValue(a2, L"AttestationLevel", (unsigned int *)a1 + 52, 0);
            v7 = v13;
            if ( !v13
              || (Logger::TraceError(
                    L"%s: %s failed with win32 error code: 0x%08x.",
                    L"JoinStatusStorage::ReadDeviceKey",
                    L"RegistryPath::ReadDwordValue",
                    v13),
                  a3) )
            {
              v14 = RegistryPath::ReadDwordValue(a2, L"AikCertStatus", (unsigned int *)a1 + 53, 0);
              v7 = v14;
              if ( !v14
                || (Logger::TraceError(
                      L"%s: %s failed with win32 error code: 0x%08x.",
                      L"JoinStatusStorage::ReadDeviceKey",
                      L"RegistryPath::ReadDwordValue",
                      v14),
                    a3) )
              {
                SafeFree(*((void **)a1 + 29));
                *((_QWORD *)a1 + 29) = 0;
                v15 = RegistryPath::ReadStringValue(a2, L"RbacResourceId", (unsigned __int16 **)a1 + 29);
                v7 = v15;
                if ( !v15
                  || (Logger::TraceError(
                        L"%s: %s failed with win32 error code: 0x%08x.",
                        L"JoinStatusStorage::ReadDeviceKey",
                        L"RegistryPath::ReadStringValue",
                        v15),
                      a3) )
                {
                  SafeFree(*((void **)a1 + 30));
                  *((_QWORD *)a1 + 30) = 0;
                  v16 = RegistryPath::ReadStringValue(a2, L"DeviceDisplayName", (unsigned __int16 **)a1 + 30);
                  v7 = v16;
                  if ( !v16
                    || (Logger::TraceError(
                          L"%s: %s failed with win32 error code: 0x%08x.",
                          L"JoinStatusStorage::ReadDeviceKey",
                          L"RegistryPath::ReadStringValue",
                          v16),
                        a3) )
                  {
                    SafeFree(*((void **)a1 + 31));
                    *((_QWORD *)a1 + 31) = 0;
                    v17 = RegistryPath::ReadStringValue(a2, L"OsVersion", (unsigned __int16 **)a1 + 31);
                    v7 = v17;
                    if ( !v17
                      || (Logger::TraceError(
                            L"%s: %s failed with win32 error code: 0x%08x.",
                            L"JoinStatusStorage::ReadDeviceKey",
                            L"RegistryPath::ReadStringValue",
                            v17),
                          a3) )
                    {
                      v18 = RegistryPath::ReadDwordValue(a2, L"DdidUpToDate", (unsigned int *)a1 + 64, 0);
                      v7 = v18;
                      if ( !v18
                        || (Logger::TraceError(
                              L"%s: %s failed with win32 error code: 0x%08x.",
                              L"JoinStatusStorage::ReadDeviceKey",
                              L"RegistryPath::ReadDwordValue",
                              v18),
                            a3) )
                      {
                        SafeFree(*((void **)a1 + 34));
                        *((_QWORD *)a1 + 34) = 0;
                        v19 = RegistryPath::ReadStringValue(a2, L"DnsFullyQualifiedName", (unsigned __int16 **)a1 + 34);
                        v7 = v19;
                        if ( !v19
                          || (Logger::TraceError(
                                L"%s: %s failed with win32 error code: 0x%08x.",
                                L"JoinStatusStorage::ReadDeviceKey",
                                L"RegistryPath::ReadStringValue",
                                v19),
                              a3) )
                        {
                          QwordValue = RegistryPath::ReadQwordValue(a2, v20, (__int64 *)a1 + 33, v21);
                          v7 = QwordValue;
                          if ( !QwordValue
                            || (Logger::TraceError(
                                  L"%s: %s failed with win32 error code: 0x%08x.",
                                  L"JoinStatusStorage::ReadDeviceKey",
                                  L"RegistryPath::ReadQwordValue",
                                  QwordValue),
                                a3) )
                          {
                            if ( a3 )
                              v7 = 0;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( *v8 && *((_QWORD *)a1 + 2) && v7 != 2 )
  {
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
    return (unsigned int)v7;
  }
  else
  {
    Logger::TraceError(
      L"%s: Failed to read one or more join status entries from the registry.",
      L"JoinStatusStorage::ReadDeviceKey");
    return 2149318678LL;
  }
}

```

## disassembly

```asm
0x18008d02c  push    rbx
0x18008d02e  push    rbp
0x18008d02f  push    rsi
0x18008d030  push    rdi
0x18008d031  push    r12
0x18008d033  push    r14
0x18008d035  push    r15
0x18008d037  sub     rsp, 20h
0x18008d03b  mov     r15, rcx
0x18008d03e  mov     r14d, r8d
0x18008d041  mov     rcx, rdx; this
0x18008d044  mov     r12, rdx
0x18008d047  call    ?OpenSubKey@RegistryPath@@QEAAKKH@Z; RegistryPath::OpenSubKey(ulong,int)
0x18008d04c  mov     ebx, eax
0x18008d04e  test    eax, eax
0x18008d050  jz      short loc_18008D07B
0x18008d052  lea     rsi, aJoinstatusstor; "JoinStatusStorage::ReadDeviceKey"
0x18008d059  mov     r9d, eax
0x18008d05c  mov     rdx, rsi
0x18008d05f  lea     r8, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x18008d066  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18008d06d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d072  lea     rdi, [r15+8]
0x18008d076  jmp     loc_18008D3B6
0x18008d07b  lea     rdi, [r15+8]
0x18008d07f  mov     rcx, [rdi]; void *
0x18008d082  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d087  mov     r8, rdi; unsigned __int16 **
0x18008d08a  mov     qword ptr [rdi], 0
0x18008d091  lea     rdx, aIdpdomain; "IdpDomain"
0x18008d098  mov     rcx, r12; this
0x18008d09b  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d0a0  lea     rsi, aJoinstatusstor; "JoinStatusStorage::ReadDeviceKey"
0x18008d0a7  mov     ebx, eax
0x18008d0a9  lea     rbp, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18008d0b0  test    eax, eax
0x18008d0b2  jz      short loc_18008D0D2
0x18008d0b4  mov     r9d, eax
0x18008d0b7  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18008d0be  mov     rdx, rsi
0x18008d0c1  mov     rcx, rbp; unsigned __int16 *
0x18008d0c4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d0c9  test    r14d, r14d
0x18008d0cc  jz      loc_18008D3B6
0x18008d0d2  lea     rbx, [r15+10h]
0x18008d0d6  mov     rcx, [rbx]; void *
0x18008d0d9  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d0de  mov     r8, rbx; unsigned __int16 **
0x18008d0e1  mov     qword ptr [rbx], 0
0x18008d0e8  lea     rdx, aTenantid_0; "TenantId"
0x18008d0ef  mov     rcx, r12; this
0x18008d0f2  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d0f7  mov     ebx, eax
0x18008d0f9  test    eax, eax
0x18008d0fb  jz      short loc_18008D11B
0x18008d0fd  mov     r9d, eax
0x18008d100  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18008d107  mov     rdx, rsi
0x18008d10a  mov     rcx, rbp; unsigned __int16 *
0x18008d10d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d112  test    r14d, r14d
0x18008d115  jz      loc_18008D3B6
0x18008d11b  lea     rbx, [r15+18h]
0x18008d11f  mov     rcx, [rbx]; void *
0x18008d122  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d127  mov     r8, rbx; unsigned __int16 **
0x18008d12a  mov     qword ptr [rbx], 0
0x18008d131  lea     rdx, aUseremail; "UserEmail"
0x18008d138  mov     rcx, r12; this
0x18008d13b  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d140  mov     ebx, eax
0x18008d142  test    eax, eax
0x18008d144  jz      short loc_18008D164
0x18008d146  mov     r9d, eax
0x18008d149  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18008d150  mov     rdx, rsi
0x18008d153  mov     rcx, rbp; unsigned __int16 *
0x18008d156  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d15b  test    r14d, r14d
0x18008d15e  jz      loc_18008D3B6
0x18008d164  lea     r8, [r15+0D8h]; unsigned int *
0x18008d16b  xor     r9d, r9d; unsigned int
0x18008d16e  lea     rdx, aTransportkeyst; "TransportKeyStatus"
0x18008d175  mov     rcx, r12; this
0x18008d178  call    ?ReadDwordValue@RegistryPath@@QEBAKPEBGPEAKK@Z; RegistryPath::ReadDwordValue(ushort const *,ulong *,ulong)
0x18008d17d  mov     ebx, eax
0x18008d17f  test    eax, eax
0x18008d181  jz      short loc_18008D1A1
0x18008d183  mov     r9d, eax
0x18008d186  lea     r8, aRegistrypathRe_2; "RegistryPath::ReadDwordValue"
0x18008d18d  mov     rdx, rsi
0x18008d190  mov     rcx, rbp; unsigned __int16 *
0x18008d193  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d198  test    r14d, r14d
0x18008d19b  jz      loc_18008D3B6
0x18008d1a1  lea     r8, [r15+0D0h]; unsigned int *
0x18008d1a8  xor     r9d, r9d; unsigned int
0x18008d1ab  lea     rdx, aAttestationlev; "AttestationLevel"
0x18008d1b2  mov     rcx, r12; this
0x18008d1b5  call    ?ReadDwordValue@RegistryPath@@QEBAKPEBGPEAKK@Z; RegistryPath::ReadDwordValue(ushort const *,ulong *,ulong)
0x18008d1ba  mov     ebx, eax
0x18008d1bc  test    eax, eax
0x18008d1be  jz      short loc_18008D1DE
0x18008d1c0  mov     r9d, eax
0x18008d1c3  lea     r8, aRegistrypathRe_2; "RegistryPath::ReadDwordValue"
0x18008d1ca  mov     rdx, rsi
0x18008d1cd  mov     rcx, rbp; unsigned __int16 *
0x18008d1d0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d1d5  test    r14d, r14d
0x18008d1d8  jz      loc_18008D3B6
0x18008d1de  lea     r8, [r15+0D4h]; unsigned int *
0x18008d1e5  xor     r9d, r9d; unsigned int
0x18008d1e8  lea     rdx, aAikcertstatus; "AikCertStatus"
0x18008d1ef  mov     rcx, r12; this
0x18008d1f2  call    ?ReadDwordValue@RegistryPath@@QEBAKPEBGPEAKK@Z; RegistryPath::ReadDwordValue(ushort const *,ulong *,ulong)
0x18008d1f7  mov     ebx, eax
0x18008d1f9  test    eax, eax
0x18008d1fb  jz      short loc_18008D21B
0x18008d1fd  mov     r9d, eax
0x18008d200  lea     r8, aRegistrypathRe_2; "RegistryPath::ReadDwordValue"
0x18008d207  mov     rdx, rsi
0x18008d20a  mov     rcx, rbp; unsigned __int16 *
0x18008d20d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d212  test    r14d, r14d
0x18008d215  jz      loc_18008D3B6
0x18008d21b  lea     rbx, [r15+0E8h]
0x18008d222  mov     rcx, [rbx]; void *
0x18008d225  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d22a  mov     r8, rbx; unsigned __int16 **
0x18008d22d  mov     qword ptr [rbx], 0
0x18008d234  lea     rdx, aRbacresourceid; "RbacResourceId"
0x18008d23b  mov     rcx, r12; this
0x18008d23e  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d243  mov     ebx, eax
0x18008d245  test    eax, eax
0x18008d247  jz      short loc_18008D267
0x18008d249  mov     r9d, eax
0x18008d24c  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18008d253  mov     rdx, rsi
0x18008d256  mov     rcx, rbp; unsigned __int16 *
0x18008d259  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d25e  test    r14d, r14d
0x18008d261  jz      loc_18008D3B6
0x18008d267  lea     rbx, [r15+0F0h]
0x18008d26e  mov     rcx, [rbx]; void *
0x18008d271  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d276  mov     r8, rbx; unsigned __int16 **
0x18008d279  mov     qword ptr [rbx], 0
0x18008d280  lea     rdx, aDevicedisplayn; "DeviceDisplayName"
0x18008d287  mov     rcx, r12; this
0x18008d28a  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d28f  mov     ebx, eax
0x18008d291  test    eax, eax
0x18008d293  jz      short loc_18008D2B3
0x18008d295  mov     r9d, eax
0x18008d298  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18008d29f  mov     rdx, rsi
0x18008d2a2  mov     rcx, rbp; unsigned __int16 *
0x18008d2a5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d2aa  test    r14d, r14d
0x18008d2ad  jz      loc_18008D3B6
0x18008d2b3  lea     rbx, [r15+0F8h]
0x18008d2ba  mov     rcx, [rbx]; void *
0x18008d2bd  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d2c2  mov     r8, rbx; unsigned __int16 **
0x18008d2c5  mov     qword ptr [rbx], 0
0x18008d2cc  lea     rdx, aOsversion; "OsVersion"
0x18008d2d3  mov     rcx, r12; this
0x18008d2d6  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d2db  mov     ebx, eax
0x18008d2dd  test    eax, eax
0x18008d2df  jz      short loc_18008D2FF
0x18008d2e1  mov     r9d, eax
0x18008d2e4  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18008d2eb  mov     rdx, rsi
0x18008d2ee  mov     rcx, rbp; unsigned __int16 *
0x18008d2f1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d2f6  test    r14d, r14d
0x18008d2f9  jz      loc_18008D3B6
0x18008d2ff  lea     r8, [r15+100h]; unsigned int *
0x18008d306  xor     r9d, r9d; unsigned int
0x18008d309  lea     rdx, aDdiduptodate; "DdidUpToDate"
0x18008d310  mov     rcx, r12; this
0x18008d313  call    ?ReadDwordValue@RegistryPath@@QEBAKPEBGPEAKK@Z; RegistryPath::ReadDwordValue(ushort const *,ulong *,ulong)
0x18008d318  mov     ebx, eax
0x18008d31a  test    eax, eax
0x18008d31c  jz      short loc_18008D338
0x18008d31e  mov     r9d, eax
0x18008d321  lea     r8, aRegistrypathRe_2; "RegistryPath::ReadDwordValue"
0x18008d328  mov     rdx, rsi
0x18008d32b  mov     rcx, rbp; unsigned __int16 *
0x18008d32e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d333  test    r14d, r14d
0x18008d336  jz      short loc_18008D3B6
0x18008d338  lea     rbx, [r15+110h]
0x18008d33f  mov     rcx, [rbx]; void *
0x18008d342  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d347  mov     r8, rbx; unsigned __int16 **
0x18008d34a  mov     qword ptr [rbx], 0
0x18008d351  lea     rdx, aDnsfullyqualif; "DnsFullyQualifiedName"
0x18008d358  mov     rcx, r12; this
0x18008d35b  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d360  mov     ebx, eax
0x18008d362  test    eax, eax
0x18008d364  jz      short loc_18008D380
0x18008d366  mov     r9d, eax
0x18008d369  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18008d370  mov     rdx, rsi
0x18008d373  mov     rcx, rbp; unsigned __int16 *
0x18008d376  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d37b  test    r14d, r14d
0x18008d37e  jz      short loc_18008D3B6
0x18008d380  lea     r8, [r15+108h]; __int64 *
0x18008d387  mov     rcx, r12; this
0x18008d38a  call    ?ReadQwordValue@RegistryPath@@QEBAKPEBGPEA_J_J@Z; RegistryPath::ReadQwordValue(ushort const *,__int64 *,__int64)
0x18008d38f  mov     ebx, eax
0x18008d391  test    eax, eax
0x18008d393  jz      short loc_18008D3AF
0x18008d395  mov     r9d, eax
0x18008d398  lea     r8, aRegistrypathRe_0; "RegistryPath::ReadQwordValue"
0x18008d39f  mov     rdx, rsi
0x18008d3a2  mov     rcx, rbp; unsigned __int16 *
0x18008d3a5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d3aa  test    r14d, r14d
0x18008d3ad  jz      short loc_18008D3B6
0x18008d3af  test    r14d, r14d
0x18008d3b2  jz      short loc_18008D3B6
0x18008d3b4  xor     ebx, ebx
0x18008d3b6  cmp     qword ptr [rdi], 0
0x18008d3ba  jz      short loc_18008D3D9
0x18008d3bc  cmp     qword ptr [r15+10h], 0
0x18008d3c1  jz      short loc_18008D3D9
0x18008d3c3  cmp     ebx, 2
0x18008d3c6  jz      short loc_18008D3D9
0x18008d3c8  test    ebx, ebx
0x18008d3ca  jle     short loc_18008D3D5
0x18008d3cc  movzx   ebx, bx
0x18008d3cf  or      ebx, 80070000h
0x18008d3d5  mov     eax, ebx
0x18008d3d7  jmp     short loc_18008D3ED
0x18008d3d9  mov     rdx, rsi
0x18008d3dc  lea     rcx, aSFailedToReadO; "%s: Failed to read one or more join sta"...
0x18008d3e3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d3e8  mov     eax, 801C0016h
0x18008d3ed  add     rsp, 20h
0x18008d3f1  pop     r15
0x18008d3f3  pop     r14
0x18008d3f5  pop     r12
0x18008d3f7  pop     rdi
0x18008d3f8  pop     rsi
0x18008d3f9  pop     rbp
0x18008d3fa  pop     rbx
0x18008d3fb  retn
```
