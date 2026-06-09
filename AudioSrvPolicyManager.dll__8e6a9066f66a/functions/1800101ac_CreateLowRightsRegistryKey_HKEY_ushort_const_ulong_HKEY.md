# CreateLowRightsRegistryKey(HKEY__ *,ushort const *,ulong,HKEY__ * *)

- ea: `0x1800101ac`
- end: `0x180010395`
- name: `?CreateLowRightsRegistryKey@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z`
- size: `489`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012c1c`
- `0x180012fb0`

## callees

- `0x18000a384`
- `0x18000fea4`
- `0x1800101ac`
- `0x18001039c`
- `0x1800109d0`
- `0x180010a00`
- `0x18002acfc`
- `0x180047ce0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800102d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800102f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010349`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800102d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800102f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010349`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010297`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010389`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010297`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010389`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180010265`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180010265`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateLowRightsRegistryKey(HKEY a1, const unsigned __int16 *a2, int a3, HKEY *a4)
{
  int v8; // eax
  __int64 v9; // r8
  unsigned __int16 *v10; // r9
  unsigned int LastError; // ebx
  LSTATUS v12; // eax
  signed int v13; // edi
  const char *v14; // r9
  HKEY v15; // rax
  int v17; // eax
  unsigned int v18; // [rsp+20h] [rbp-49h]
  int v19; // [rsp+20h] [rbp-49h]
  HKEY hKey; // [rsp+50h] [rbp-19h] BYREF
  PSID Sid[2]; // [rsp+58h] [rbp-11h] BYREF
  char v22; // [rsp+68h] [rbp-1h]
  struct _SECURITY_ATTRIBUTES v23; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  memset(&v23, 0, sizeof(v23));
  v23.nLength = 24;
  v8 = DetermineLowRightsKeySecurityDescriptor(a1, &v23.lpSecurityDescriptor);
  LastError = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
      (const char *)(unsigned int)v8,
      v18);
    return LastError;
  }
  Sid[1] = &v23;
  v22 = 1;
  hKey = 0;
  v12 = SafeRegCreateKeyEx(a1, a2, v9, v10, v18, a3 | ((a3 & 0x20006) != 0 ? 655360 : 0x20000), &v23, &hKey);
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( v13 < 0 )
  {
    LastError = -2147024891;
    if ( v13 != -2147024891 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
        (const char *)(unsigned int)v13,
        v19);
      if ( hKey )
        RegCloseKey(hKey);
      LastError = v13;
      goto LABEL_10;
    }
  }
  else
  {
    Sid[0] = 0;
    if ( ConvertStringSidToSidW(L"LW", Sid) )
    {
      if ( (int)SetRegistryKeyIntegrityLevel(hKey, Sid[0]) >= 0
        || (v17 = SetRegistryHandleIntegrityLevel(hKey, Sid[0]), LastError = v17, v17 >= 0) )
      {
        v15 = hKey;
        hKey = 0;
        *a4 = v15;
        LocalFree(Sid[0]);
        if ( hKey )
          RegCloseKey(hKey);
        LastError = 0;
        goto LABEL_10;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
        (const char *)(unsigned int)v17,
        v19);
      LocalFree(Sid[0]);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x95,
                    (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
                    v14);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
LABEL_10:
  operator delete(v23.lpSecurityDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x1800101ac  push    rbp
0x1800101ae  push    rbx
0x1800101af  push    rsi
0x1800101b0  push    rdi
0x1800101b1  push    r14
0x1800101b3  push    r15
0x1800101b5  lea     rbp, [rsp-2Fh]
0x1800101ba  sub     rsp, 98h
0x1800101c1  mov     rsi, r9
0x1800101c4  mov     r14d, r8d
0x1800101c7  mov     r15, rdx
0x1800101ca  mov     rdi, rcx
0x1800101cd  xorps   xmm0, xmm0
0x1800101d0  xor     eax, eax
0x1800101d2  movups  xmmword ptr [rbp+57h+var_50.nLength], xmm0
0x1800101d6  mov     qword ptr [rbp+57h+var_50.bInheritHandle], rax
0x1800101da  mov     [rbp+57h+var_50.nLength], 18h
0x1800101e1  lea     rdx, [rbp+57h+var_50.lpSecurityDescriptor]; void **
0x1800101e5  call    ?DetermineLowRightsKeySecurityDescriptor@@YAJPEAUHKEY__@@PEAPEAX@Z; DetermineLowRightsKeySecurityDescriptor(HKEY__ *,void * *)
0x1800101ea  mov     ebx, eax
0x1800101ec  test    eax, eax
0x1800101ee  js      loc_18001030D
0x1800101f4  lea     rax, [rbp+57h+var_50]
0x1800101f8  mov     [rbp+57h+var_60], rax
0x1800101fc  mov     [rbp+57h+var_58], 1
0x180010200  mov     eax, r14d
0x180010203  and     eax, 20006h
0x180010208  neg     eax
0x18001020a  sbb     ecx, ecx
0x18001020c  and     ecx, 80000h
0x180010212  add     ecx, 20000h
0x180010218  or      ecx, r14d
0x18001021b  mov     [rbp+57h+hKey], 0
0x180010223  lea     rax, [rbp+57h+hKey]
0x180010227  mov     [rsp+0C0h+var_88], rax; HKEY *
0x18001022c  lea     rax, [rbp+57h+var_50]
0x180010230  mov     [rsp+0C0h+var_90], rax; LPSECURITY_ATTRIBUTES
0x180010235  mov     [rsp+0C0h+samDesired], ecx; samDesired
0x180010239  mov     rdx, r15; unsigned __int16 *
0x18001023c  mov     rcx, rdi; HKEY
0x18001023f  call    ?SafeRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; SafeRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180010244  mov     edi, eax
0x180010246  test    eax, eax
0x180010248  jg      loc_1800102FF
0x18001024e  test    edi, edi
0x180010250  js      short loc_1800102C4
0x180010252  mov     [rbp+57h+Sid], 0
0x18001025a  lea     rdx, [rbp+57h+Sid]; Sid
0x18001025e  lea     rcx, StringSid; "LW"
0x180010265  call    cs:__imp_ConvertStringSidToSidW
0x18001026b  test    eax, eax
0x18001026d  jz      short loc_1800102DE
0x18001026f  mov     rdx, [rbp+57h+Sid]; pSid
0x180010273  mov     rcx, [rbp+57h+hKey]; hKey
0x180010277  call    ?SetRegistryKeyIntegrityLevel@@YAJPEAUHKEY__@@PEAX@Z; SetRegistryKeyIntegrityLevel(HKEY__ *,void *)
0x18001027c  test    eax, eax
0x18001027e  js      loc_180010356
0x180010284  mov     rax, [rbp+57h+hKey]
0x180010288  mov     [rbp+57h+hKey], 0
0x180010290  mov     [rsi], rax
0x180010293  mov     rcx, [rbp+57h+Sid]; hMem
0x180010297  call    cs:__imp_LocalFree
0x18001029d  nop
0x18001029e  mov     rcx, [rbp+57h+hKey]; hKey
0x1800102a2  test    rcx, rcx
0x1800102a5  jnz     short loc_1800102F7
0x1800102a7  xor     ebx, ebx
0x1800102a9  mov     rcx, [rbp+57h+var_50.lpSecurityDescriptor]; void *
0x1800102ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800102b2  mov     eax, ebx
0x1800102b4  add     rsp, 98h
0x1800102bb  pop     r15
0x1800102bd  pop     r14
0x1800102bf  pop     rdi
0x1800102c0  pop     rsi
0x1800102c1  pop     rbx
0x1800102c2  pop     rbp
0x1800102c3  retn
0x1800102c4  mov     ebx, 80070005h
0x1800102c9  cmp     edi, ebx
0x1800102cb  jnz     short loc_180010327
0x1800102cd  mov     rcx, [rbp+57h+hKey]; hKey
0x1800102d1  test    rcx, rcx
0x1800102d4  jz      short loc_1800102A9
0x1800102d6  call    cs:__imp_RegCloseKey
0x1800102dc  jmp     short loc_1800102A9
0x1800102de  mov     rcx, [rbp+5Fh]; this
0x1800102e2  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x1800102e9  mov     edx, 95h; void *
0x1800102ee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800102f3  mov     ebx, eax
0x1800102f5  jmp     short loc_1800102CD
0x1800102f7  call    cs:__imp_RegCloseKey
0x1800102fd  jmp     short loc_1800102A7
0x1800102ff  movzx   edi, ax
0x180010302  or      edi, 80070000h
0x180010308  jmp     loc_18001024E
0x18001030d  mov     rcx, [rbp+5Fh]; this
0x180010311  mov     r9d, ebx; char *
0x180010314  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x18001031b  mov     edx, 87h; void *
0x180010320  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010325  jmp     short loc_1800102B2
0x180010327  mov     rcx, [rbp+5Fh]; this
0x18001032b  mov     r9d, edi; char *
0x18001032e  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x180010335  mov     edx, 91h; void *
0x18001033a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001033f  nop
0x180010340  mov     rcx, [rbp+57h+hKey]; hKey
0x180010344  test    rcx, rcx
0x180010347  jz      short loc_18001034F
0x180010349  call    cs:__imp_RegCloseKey
0x18001034f  mov     ebx, edi
0x180010351  jmp     loc_1800102A9
0x180010356  mov     rdx, [rbp+57h+Sid]; void *
0x18001035a  mov     rcx, [rbp+57h+hKey]; Handle
0x18001035e  call    ?SetRegistryHandleIntegrityLevel@@YAJPEAUHKEY__@@PEAX@Z; SetRegistryHandleIntegrityLevel(HKEY__ *,void *)
0x180010363  mov     ebx, eax
0x180010365  test    eax, eax
0x180010367  jns     loc_180010284
0x18001036d  mov     rcx, [rbp+5Fh]; this
0x180010371  mov     r9d, eax; char *
0x180010374  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x18001037b  mov     edx, 9Eh; void *
0x180010380  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010385  mov     rcx, [rbp+57h+Sid]; hMem
0x180010389  call    cs:__imp_LocalFree
0x18001038f  jmp     loc_1800102CD
```
