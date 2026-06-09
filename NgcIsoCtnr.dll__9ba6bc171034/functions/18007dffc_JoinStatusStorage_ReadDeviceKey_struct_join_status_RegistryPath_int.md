# JoinStatusStorage::ReadDeviceKey(struct_join_status *,RegistryPath &,int)

- ea: `0x18007dffc`
- end: `0x18007e3c0`
- name: `?ReadDeviceKey@JoinStatusStorage@@CAJPEAUstruct_join_status@@AEAVRegistryPath@@H@Z`
- size: `964`
- prototype: `static int(struct struct_join_status *, struct RegistryPath *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18007e3c8`

## callees

- `0x180079de0`
- `0x18007d1b8`
- `0x18007dffc`
- `0x180081b6c`
- `0x180081cdc`
- `0x180081d48`
- `0x180081db0`

## string_xrefs

- `0x18007e02f`: `RegistryPath::OpenSubKey`
- `0x18007e153`: `RegistryPath::ReadDwordValue`
- `0x18007e18d`: `RegistryPath::ReadDwordValue`
- `0x18007e1c7`: `RegistryPath::ReadDwordValue`
- `0x18007e2e5`: `RegistryPath::ReadDwordValue`
- `0x18007e35c`: `RegistryPath::ReadQwordValue`
- `0x18007e022`: `JoinStatusStorage::ReadDeviceKey`
- `0x18007e070`: `JoinStatusStorage::ReadDeviceKey`
- `0x18007e087`: `RegistryPath::ReadStringValue`
- `0x18007e0d0`: `RegistryPath::ReadStringValue`
- `0x18007e119`: `RegistryPath::ReadStringValue`
- `0x18007e213`: `RegistryPath::ReadStringValue`
- `0x18007e25f`: `RegistryPath::ReadStringValue`
- `0x18007e2ab`: `RegistryPath::ReadStringValue`
- `0x18007e32d`: `RegistryPath::ReadStringValue`
- `0x18007e3a0`: `%s: Failed to read one or more join status entries from the registry.`

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
  unsigned int v12; // r9d
  unsigned int DwordValue; // eax
  unsigned int v14; // r9d
  unsigned int v15; // eax
  unsigned int v16; // r9d
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // r9d
  unsigned int v22; // eax
  unsigned int v23; // eax
  const unsigned __int16 *v24; // rdx
  __int64 v25; // r9
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
          DwordValue = RegistryPath::ReadDwordValue(a2, L"TransportKeyStatus", (unsigned int *)a1 + 54, v12);
          v7 = DwordValue;
          if ( !DwordValue
            || (Logger::TraceError(
                  L"%s: %s failed with win32 error code: 0x%08x.",
                  L"JoinStatusStorage::ReadDeviceKey",
                  L"RegistryPath::ReadDwordValue",
                  DwordValue),
                a3) )
          {
            v15 = RegistryPath::ReadDwordValue(a2, L"AttestationLevel", (unsigned int *)a1 + 52, v14);
            v7 = v15;
            if ( !v15
              || (Logger::TraceError(
                    L"%s: %s failed with win32 error code: 0x%08x.",
                    L"JoinStatusStorage::ReadDeviceKey",
                    L"RegistryPath::ReadDwordValue",
                    v15),
                  a3) )
            {
              v17 = RegistryPath::ReadDwordValue(a2, L"AikCertStatus", (unsigned int *)a1 + 53, v16);
              v7 = v17;
              if ( !v17
                || (Logger::TraceError(
                      L"%s: %s failed with win32 error code: 0x%08x.",
                      L"JoinStatusStorage::ReadDeviceKey",
                      L"RegistryPath::ReadDwordValue",
                      v17),
                    a3) )
              {
                SafeFree(*((void **)a1 + 29));
                *((_QWORD *)a1 + 29) = 0;
                v18 = RegistryPath::ReadStringValue(a2, L"RbacResourceId", (unsigned __int16 **)a1 + 29);
                v7 = v18;
                if ( !v18
                  || (Logger::TraceError(
                        L"%s: %s failed with win32 error code: 0x%08x.",
                        L"JoinStatusStorage::ReadDeviceKey",
                        L"RegistryPath::ReadStringValue",
                        v18),
                      a3) )
                {
                  SafeFree(*((void **)a1 + 30));
                  *((_QWORD *)a1 + 30) = 0;
                  v19 = RegistryPath::ReadStringValue(a2, L"DeviceDisplayName", (unsigned __int16 **)a1 + 30);
                  v7 = v19;
                  if ( !v19
                    || (Logger::TraceError(
                          L"%s: %s failed with win32 error code: 0x%08x.",
                          L"JoinStatusStorage::ReadDeviceKey",
                          L"RegistryPath::ReadStringValue",
                          v19),
                        a3) )
                  {
                    SafeFree(*((void **)a1 + 31));
                    *((_QWORD *)a1 + 31) = 0;
                    v20 = RegistryPath::ReadStringValue(a2, L"OsVersion", (unsigned __int16 **)a1 + 31);
                    v7 = v20;
                    if ( !v20
                      || (Logger::TraceError(
                            L"%s: %s failed with win32 error code: 0x%08x.",
                            L"JoinStatusStorage::ReadDeviceKey",
                            L"RegistryPath::ReadStringValue",
                            v20),
                          a3) )
                    {
                      v22 = RegistryPath::ReadDwordValue(a2, L"DdidUpToDate", (unsigned int *)a1 + 64, v21);
                      v7 = v22;
                      if ( !v22
                        || (Logger::TraceError(
                              L"%s: %s failed with win32 error code: 0x%08x.",
                              L"JoinStatusStorage::ReadDeviceKey",
                              L"RegistryPath::ReadDwordValue",
                              v22),
                            a3) )
                      {
                        SafeFree(*((void **)a1 + 34));
                        *((_QWORD *)a1 + 34) = 0;
                        v23 = RegistryPath::ReadStringValue(a2, L"DnsFullyQualifiedName", (unsigned __int16 **)a1 + 34);
                        v7 = v23;
                        if ( !v23
                          || (Logger::TraceError(
                                L"%s: %s failed with win32 error code: 0x%08x.",
                                L"JoinStatusStorage::ReadDeviceKey",
                                L"RegistryPath::ReadStringValue",
                                v23),
                              a3) )
                        {
                          QwordValue = RegistryPath::ReadQwordValue(a2, v24, (__int64 *)a1 + 33, v25);
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
0x18007dffc  push    rbx
0x18007dffe  push    rbp
0x18007dfff  push    rsi
0x18007e000  push    rdi
0x18007e001  push    r12
0x18007e003  push    r14
0x18007e005  push    r15
0x18007e007  sub     rsp, 20h
0x18007e00b  mov     r15, rcx
0x18007e00e  mov     r14d, r8d
0x18007e011  mov     rcx, rdx; this
0x18007e014  mov     r12, rdx
0x18007e017  call    ?OpenSubKey@RegistryPath@@QEAAKKH@Z; RegistryPath::OpenSubKey(ulong,int)
0x18007e01c  mov     ebx, eax
0x18007e01e  test    eax, eax
0x18007e020  jz      short loc_18007E04B
0x18007e022  lea     rsi, aJoinstatusstor; "JoinStatusStorage::ReadDeviceKey"
0x18007e029  mov     r9d, eax
0x18007e02c  mov     rdx, rsi
0x18007e02f  lea     r8, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x18007e036  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18007e03d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e042  lea     rdi, [r15+8]
0x18007e046  jmp     loc_18007E37A
0x18007e04b  lea     rdi, [r15+8]
0x18007e04f  mov     rcx, [rdi]; void *
0x18007e052  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e057  mov     r8, rdi; unsigned __int16 **
0x18007e05a  mov     qword ptr [rdi], 0
0x18007e061  lea     rdx, aIdpdomain; "IdpDomain"
0x18007e068  mov     rcx, r12; this
0x18007e06b  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e070  lea     rsi, aJoinstatusstor; "JoinStatusStorage::ReadDeviceKey"
0x18007e077  mov     ebx, eax
0x18007e079  lea     rbp, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18007e080  test    eax, eax
0x18007e082  jz      short loc_18007E0A2
0x18007e084  mov     r9d, eax
0x18007e087  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18007e08e  mov     rdx, rsi
0x18007e091  mov     rcx, rbp; unsigned __int16 *
0x18007e094  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e099  test    r14d, r14d
0x18007e09c  jz      loc_18007E37A
0x18007e0a2  lea     rbx, [r15+10h]
0x18007e0a6  mov     rcx, [rbx]; void *
0x18007e0a9  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e0ae  mov     r8, rbx; unsigned __int16 **
0x18007e0b1  mov     qword ptr [rbx], 0
0x18007e0b8  lea     rdx, aTenantid; "TenantId"
0x18007e0bf  mov     rcx, r12; this
0x18007e0c2  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e0c7  mov     ebx, eax
0x18007e0c9  test    eax, eax
0x18007e0cb  jz      short loc_18007E0EB
0x18007e0cd  mov     r9d, eax
0x18007e0d0  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18007e0d7  mov     rdx, rsi
0x18007e0da  mov     rcx, rbp; unsigned __int16 *
0x18007e0dd  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e0e2  test    r14d, r14d
0x18007e0e5  jz      loc_18007E37A
0x18007e0eb  lea     rbx, [r15+18h]
0x18007e0ef  mov     rcx, [rbx]; void *
0x18007e0f2  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e0f7  mov     r8, rbx; unsigned __int16 **
0x18007e0fa  mov     qword ptr [rbx], 0
0x18007e101  lea     rdx, aUseremail; "UserEmail"
0x18007e108  mov     rcx, r12; this
0x18007e10b  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e110  mov     ebx, eax
0x18007e112  test    eax, eax
0x18007e114  jz      short loc_18007E134
0x18007e116  mov     r9d, eax
0x18007e119  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18007e120  mov     rdx, rsi
0x18007e123  mov     rcx, rbp; unsigned __int16 *
0x18007e126  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e12b  test    r14d, r14d
0x18007e12e  jz      loc_18007E37A
0x18007e134  lea     r8, [r15+0D8h]; unsigned int *
0x18007e13b  mov     rcx, r12; this
0x18007e13e  lea     rdx, aTransportkeyst; "TransportKeyStatus"
0x18007e145  call    ?ReadDwordValue@RegistryPath@@QEBAKPEBGPEAKK@Z; RegistryPath::ReadDwordValue(ushort const *,ulong *,ulong)
0x18007e14a  mov     ebx, eax
0x18007e14c  test    eax, eax
0x18007e14e  jz      short loc_18007E16E
0x18007e150  mov     r9d, eax
0x18007e153  lea     r8, aRegistrypathRe_1; "RegistryPath::ReadDwordValue"
0x18007e15a  mov     rdx, rsi
0x18007e15d  mov     rcx, rbp; unsigned __int16 *
0x18007e160  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e165  test    r14d, r14d
0x18007e168  jz      loc_18007E37A
0x18007e16e  lea     r8, [r15+0D0h]; unsigned int *
0x18007e175  mov     rcx, r12; this
0x18007e178  lea     rdx, aAttestationlev; "AttestationLevel"
0x18007e17f  call    ?ReadDwordValue@RegistryPath@@QEBAKPEBGPEAKK@Z; RegistryPath::ReadDwordValue(ushort const *,ulong *,ulong)
0x18007e184  mov     ebx, eax
0x18007e186  test    eax, eax
0x18007e188  jz      short loc_18007E1A8
0x18007e18a  mov     r9d, eax
0x18007e18d  lea     r8, aRegistrypathRe_1; "RegistryPath::ReadDwordValue"
0x18007e194  mov     rdx, rsi
0x18007e197  mov     rcx, rbp; unsigned __int16 *
0x18007e19a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e19f  test    r14d, r14d
0x18007e1a2  jz      loc_18007E37A
0x18007e1a8  lea     r8, [r15+0D4h]; unsigned int *
0x18007e1af  mov     rcx, r12; this
0x18007e1b2  lea     rdx, aAikcertstatus; "AikCertStatus"
0x18007e1b9  call    ?ReadDwordValue@RegistryPath@@QEBAKPEBGPEAKK@Z; RegistryPath::ReadDwordValue(ushort const *,ulong *,ulong)
0x18007e1be  mov     ebx, eax
0x18007e1c0  test    eax, eax
0x18007e1c2  jz      short loc_18007E1E2
0x18007e1c4  mov     r9d, eax
0x18007e1c7  lea     r8, aRegistrypathRe_1; "RegistryPath::ReadDwordValue"
0x18007e1ce  mov     rdx, rsi
0x18007e1d1  mov     rcx, rbp; unsigned __int16 *
0x18007e1d4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e1d9  test    r14d, r14d
0x18007e1dc  jz      loc_18007E37A
0x18007e1e2  lea     rbx, [r15+0E8h]
0x18007e1e9  mov     rcx, [rbx]; void *
0x18007e1ec  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e1f1  mov     r8, rbx; unsigned __int16 **
0x18007e1f4  mov     qword ptr [rbx], 0
0x18007e1fb  lea     rdx, aRbacresourceid; "RbacResourceId"
0x18007e202  mov     rcx, r12; this
0x18007e205  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e20a  mov     ebx, eax
0x18007e20c  test    eax, eax
0x18007e20e  jz      short loc_18007E22E
0x18007e210  mov     r9d, eax
0x18007e213  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18007e21a  mov     rdx, rsi
0x18007e21d  mov     rcx, rbp; unsigned __int16 *
0x18007e220  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e225  test    r14d, r14d
0x18007e228  jz      loc_18007E37A
0x18007e22e  lea     rbx, [r15+0F0h]
0x18007e235  mov     rcx, [rbx]; void *
0x18007e238  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e23d  mov     r8, rbx; unsigned __int16 **
0x18007e240  mov     qword ptr [rbx], 0
0x18007e247  lea     rdx, aDevicedisplayn; "DeviceDisplayName"
0x18007e24e  mov     rcx, r12; this
0x18007e251  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e256  mov     ebx, eax
0x18007e258  test    eax, eax
0x18007e25a  jz      short loc_18007E27A
0x18007e25c  mov     r9d, eax
0x18007e25f  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18007e266  mov     rdx, rsi
0x18007e269  mov     rcx, rbp; unsigned __int16 *
0x18007e26c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e271  test    r14d, r14d
0x18007e274  jz      loc_18007E37A
0x18007e27a  lea     rbx, [r15+0F8h]
0x18007e281  mov     rcx, [rbx]; void *
0x18007e284  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e289  mov     r8, rbx; unsigned __int16 **
0x18007e28c  mov     qword ptr [rbx], 0
0x18007e293  lea     rdx, aOsversion; "OsVersion"
0x18007e29a  mov     rcx, r12; this
0x18007e29d  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e2a2  mov     ebx, eax
0x18007e2a4  test    eax, eax
0x18007e2a6  jz      short loc_18007E2C6
0x18007e2a8  mov     r9d, eax
0x18007e2ab  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18007e2b2  mov     rdx, rsi
0x18007e2b5  mov     rcx, rbp; unsigned __int16 *
0x18007e2b8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e2bd  test    r14d, r14d
0x18007e2c0  jz      loc_18007E37A
0x18007e2c6  lea     r8, [r15+100h]; unsigned int *
0x18007e2cd  mov     rcx, r12; this
0x18007e2d0  lea     rdx, aDdiduptodate; "DdidUpToDate"
0x18007e2d7  call    ?ReadDwordValue@RegistryPath@@QEBAKPEBGPEAKK@Z; RegistryPath::ReadDwordValue(ushort const *,ulong *,ulong)
0x18007e2dc  mov     ebx, eax
0x18007e2de  test    eax, eax
0x18007e2e0  jz      short loc_18007E2FC
0x18007e2e2  mov     r9d, eax
0x18007e2e5  lea     r8, aRegistrypathRe_1; "RegistryPath::ReadDwordValue"
0x18007e2ec  mov     rdx, rsi
0x18007e2ef  mov     rcx, rbp; unsigned __int16 *
0x18007e2f2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e2f7  test    r14d, r14d
0x18007e2fa  jz      short loc_18007E37A
0x18007e2fc  lea     rbx, [r15+110h]
0x18007e303  mov     rcx, [rbx]; void *
0x18007e306  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e30b  mov     r8, rbx; unsigned __int16 **
0x18007e30e  mov     qword ptr [rbx], 0
0x18007e315  lea     rdx, aDnsfullyqualif; "DnsFullyQualifiedName"
0x18007e31c  mov     rcx, r12; this
0x18007e31f  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e324  mov     ebx, eax
0x18007e326  test    eax, eax
0x18007e328  jz      short loc_18007E344
0x18007e32a  mov     r9d, eax
0x18007e32d  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18007e334  mov     rdx, rsi
0x18007e337  mov     rcx, rbp; unsigned __int16 *
0x18007e33a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e33f  test    r14d, r14d
0x18007e342  jz      short loc_18007E37A
0x18007e344  lea     r8, [r15+108h]; __int64 *
0x18007e34b  mov     rcx, r12; this
0x18007e34e  call    ?ReadQwordValue@RegistryPath@@QEBAKPEBGPEA_J_J@Z; RegistryPath::ReadQwordValue(ushort const *,__int64 *,__int64)
0x18007e353  mov     ebx, eax
0x18007e355  test    eax, eax
0x18007e357  jz      short loc_18007E373
0x18007e359  mov     r9d, eax
0x18007e35c  lea     r8, aRegistrypathRe_0; "RegistryPath::ReadQwordValue"
0x18007e363  mov     rdx, rsi
0x18007e366  mov     rcx, rbp; unsigned __int16 *
0x18007e369  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e36e  test    r14d, r14d
0x18007e371  jz      short loc_18007E37A
0x18007e373  test    r14d, r14d
0x18007e376  jz      short loc_18007E37A
0x18007e378  xor     ebx, ebx
0x18007e37a  cmp     qword ptr [rdi], 0
0x18007e37e  jz      short loc_18007E39D
0x18007e380  cmp     qword ptr [r15+10h], 0
0x18007e385  jz      short loc_18007E39D
0x18007e387  cmp     ebx, 2
0x18007e38a  jz      short loc_18007E39D
0x18007e38c  test    ebx, ebx
0x18007e38e  jle     short loc_18007E399
0x18007e390  movzx   ebx, bx
0x18007e393  or      ebx, 80070000h
0x18007e399  mov     eax, ebx
0x18007e39b  jmp     short loc_18007E3B1
0x18007e39d  mov     rdx, rsi
0x18007e3a0  lea     rcx, aSFailedToReadO; "%s: Failed to read one or more join sta"...
0x18007e3a7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e3ac  mov     eax, 801C0016h
0x18007e3b1  add     rsp, 20h
0x18007e3b5  pop     r15
0x18007e3b7  pop     r14
0x18007e3b9  pop     r12
0x18007e3bb  pop     rdi
0x18007e3bc  pop     rsi
0x18007e3bd  pop     rbp
0x18007e3be  pop     rbx
0x18007e3bf  retn
```
