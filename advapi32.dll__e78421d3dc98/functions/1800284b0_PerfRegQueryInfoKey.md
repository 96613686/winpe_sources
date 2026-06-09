# PerfRegQueryInfoKey

- ea: `0x1800284b0`
- end: `0x180028846`
- name: `PerfRegQueryInfoKey`
- size: `918`
- prototype: `__int64 __usercall@<rax>(HKEY@<rcx>, __int64, __int64, __int64, __int64, __int64, PULONG, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180026a7c`
- `0x1800284b0`
- `0x1800288a0`
- `0x18003b57c`

## import_xrefs

- `ntdll!NtOpenKey` at `0x1800286e0`
- `ntdll!NtOpenKey` at `0x180028761`
- `ntdll!NtOpenKey` at `0x1800286e0`
- `ntdll!NtOpenKey` at `0x180028761`
- `ntdll!NtClose` at `0x18002872a`
- `ntdll!NtClose` at `0x18002872a`
- `ntdll!RtlCopyUnicodeString` at `0x1800285b9`
- `ntdll!RtlCopyUnicodeString` at `0x180028635`
- `ntdll!RtlCopyUnicodeString` at `0x1800285b9`
- `ntdll!RtlCopyUnicodeString` at `0x180028635`
- `ntdll!NtQuerySecurityObject` at `0x180028710`
- `ntdll!NtQuerySecurityObject` at `0x180028710`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180028521`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180028521`
- `ntdll!RtlInitUnicodeString` at `0x1800285aa`
- `ntdll!RtlInitUnicodeString` at `0x180028626`
- `ntdll!RtlInitUnicodeString` at `0x1800286ab`
- `ntdll!RtlInitUnicodeString` at `0x1800285aa`
- `ntdll!RtlInitUnicodeString` at `0x180028626`
- `ntdll!RtlInitUnicodeString` at `0x1800286ab`

## string_xrefs

- `0x18002869b`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Perflib`

## pseudocode

```c
__int64 __fastcall PerfRegQueryInfoKey(
        HKEY a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        _DWORD *a5,
        _DWORD *a6,
        _DWORD *a7,
        _DWORD *a8,
        unsigned int *a9,
        PULONG a10,
        _QWORD *a11)
{
  _WORD *v14; // rcx
  _DWORD *v15; // rax
  _DWORD *v16; // rsi
  _DWORD *v17; // r14
  unsigned int *v18; // rdi
  _QWORD *v19; // rax
  unsigned int v20; // ebx
  unsigned int v21; // eax
  int v22; // esi
  PULONG v23; // rdi
  HANDLE v24; // rcx
  SECURITY_INFORMATION v25; // edx
  NTSTATUS SecurityObject; // ebx
  NTSTATUS v28; // eax
  _QWORD *v29; // rcx
  ULONG *LengthNeeded; // [rsp+20h] [rbp-A9h]
  struct _UNICODE_STRING v31; // [rsp+40h] [rbp-89h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-79h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-69h] BYREF
  struct _UNICODE_STRING v34; // [rsp+90h] [rbp-39h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v36; // [rsp+C0h] [rbp-9h]
  unsigned int v37; // [rsp+110h] [rbp+47h] BYREF
  unsigned int v38; // [rsp+118h] [rbp+4Fh] BYREF
  HANDLE KeyHandle; // [rsp+128h] [rbp+5Fh] BYREF

  v37 = 0;
  v38 = 0;
  KeyHandle = 0;
  v36 = 0;
  v31 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v34 = 0;
  RtlRunOnceExecuteOnce(qword_1800A3088, PerfpInitializeCallback, 0, 0);
  if ( *(_WORD *)(a2 + 2) >= 2u )
  {
    v14 = *(_WORD **)(a2 + 8);
    *(_WORD *)a2 = 0;
    *v14 = 0;
  }
  v15 = a5;
  v16 = a7;
  v17 = a8;
  *a4 = 0;
  v18 = a9;
  *v15 = 0;
  *a6 = 0;
  v19 = a11;
  *v16 = 2;
  *v17 = 30;
  *v18 = 0;
  if ( v19 )
    *v19 = 0;
  if ( ((unsigned __int64)(a1 + 536870892) & 0xFFFFFFFFFFFFFFEFuLL) == 0 )
  {
    v31.Buffer = 0;
    *(_DWORD *)&v31.Length = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"Counter");
    RtlCopyUnicodeString(&v31, &DestinationString);
    if ( (unsigned __int64)v31.Length + 2 <= v31.MaximumLength )
    {
      v31.Buffer[(unsigned __int64)v31.Length >> 1] = 0;
      v31.Length += 2;
    }
    v20 = PerfRegQueryValueEx(a1, &stru_180067610, &DestinationString, 0, 0, 0, &v38, 0);
    if ( v20 )
      goto LABEL_34;
    v31.Length = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"Help");
    RtlCopyUnicodeString(&v31, &DestinationString);
    if ( (unsigned __int64)v31.Length + 2 <= v31.MaximumLength )
    {
      v31.Buffer[(unsigned __int64)v31.Length >> 1] = 0;
      v31.Length += 2;
    }
    v20 = PerfRegQueryValueEx(a1, &stru_180067610, &DestinationString, 0, 0, 0, &v37, 0);
    if ( v20 )
    {
LABEL_34:
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, v20);
      *v16 = 0;
      *v17 = 0;
      return v20;
    }
    v21 = v38;
    if ( v37 > v38 )
    {
      v21 = v37;
      v38 = v37;
    }
    *v18 = v21;
  }
  v22 = 1;
  RtlInitUnicodeString(&v34, L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v34;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x3000000u, &ObjectAttributes) < 0 )
  {
    v28 = NtOpenKey(&KeyHandle, 0x2000000u, &ObjectAttributes);
    SecurityObject = v28;
    v22 = 0;
    if ( v28 < 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        return PerfpDosError(SecurityObject);
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_28:
        if ( (*((_BYTE *)v29 + 28) & 2) != 0 && *((_BYTE *)v29 + 25) >= 2u )
          WPP_SF_d(v29[2], 47, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, (unsigned int)SecurityObject);
        return PerfpDosError(SecurityObject);
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids,
        (unsigned int)v28);
LABEL_27:
      v29 = WPP_GLOBAL_Control;
      goto LABEL_28;
    }
  }
  v23 = a10;
  v24 = KeyHandle;
  LengthNeeded = a10;
  *a10 = 0;
  v25 = 7;
  if ( v22 )
    v25 = 15;
  SecurityObject = NtQuerySecurityObject(v24, v25, SecurityDescriptor, 0, LengthNeeded);
  if ( SecurityObject == -1073741789 )
    SecurityObject = 0;
  else
    *v23 = 0;
  NtClose(KeyHandle);
  if ( SecurityObject < 0 )
    goto LABEL_27;
  return 0;
}

```

## disassembly

```asm
0x1800284b0  mov     [rsp-8+arg_10], rbx
0x1800284b5  push    rbp
0x1800284b6  push    rsi
0x1800284b7  push    rdi
0x1800284b8  push    r12
0x1800284ba  push    r13
0x1800284bc  push    r14
0x1800284be  push    r15
0x1800284c0  lea     rbp, [rsp-7]
0x1800284c5  sub     rsp, 0D0h
0x1800284cc  xorps   xmm0, xmm0
0x1800284cf  xor     r12d, r12d
0x1800284d2  xorps   xmm1, xmm1
0x1800284d5  mov     [rbp+37h+arg_0], r12d
0x1800284d9  mov     rdi, r9
0x1800284dc  mov     [rbp+37h+arg_8], r12d
0x1800284e0  mov     rbx, rdx
0x1800284e3  mov     [rbp+37h+KeyHandle], r12
0x1800284e7  mov     r15, rcx
0x1800284ea  lea     rdx, PerfpInitializeCallback
0x1800284f1  xor     eax, eax
0x1800284f3  lea     rcx, qword_1800A3088
0x1800284fa  xor     r9d, r9d
0x1800284fd  mov     [rbp+37h+var_40], rax
0x180028501  xor     r8d, r8d
0x180028504  movups  xmmword ptr [rsp+100h+var_C0.Length], xmm0
0x180028509  movups  [rbp+37h+SecurityDescriptor], xmm1
0x18002850d  movups  [rbp+37h+var_50], xmm1
0x180028511  movups  xmmword ptr [rbp+37h+ObjectAttributes.Length], xmm0
0x180028515  movups  xmmword ptr [rbp+37h+ObjectAttributes.ObjectName], xmm0
0x180028519  movups  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002851d  movups  xmmword ptr [rbp+37h+var_70.Length], xmm0
0x180028521  call    cs:__imp_RtlRunOnceExecuteOnce
0x180028527  lea     r13d, [r12+2]
0x18002852c  cmp     [rbx+2], r13w
0x180028531  jb      short loc_18002853F
0x180028533  mov     rcx, [rbx+8]
0x180028537  mov     [rbx], r12w
0x18002853b  mov     [rcx], r12w
0x18002853f  mov     rax, [rbp+37h+arg_20]
0x180028543  mov     rsi, [rbp+37h+arg_30]
0x180028547  mov     r14, [rbp+37h+arg_38]
0x18002854b  mov     [rdi], r12d
0x18002854e  mov     rdi, [rbp+37h+arg_40]
0x180028555  mov     [rax], r12d
0x180028558  mov     rax, [rbp+37h+arg_28]
0x18002855c  mov     [rax], r12d
0x18002855f  mov     rax, [rbp+37h+arg_50]
0x180028566  mov     [rsi], r13d
0x180028569  mov     dword ptr [r14], 1Eh
0x180028570  mov     [rdi], r12d
0x180028573  test    rax, rax
0x180028576  jz      short loc_18002857B
0x180028578  mov     [rax], r12
0x18002857b  lea     rax, [r15+7FFFFFB0h]
0x180028582  test    rax, 0FFFFFFFFFFFFFFEFh
0x180028588  jnz     loc_18002869B
0x18002858e  xorps   xmm0, xmm0
0x180028591  mov     [rsp+100h+var_C0.Buffer], r12
0x180028596  lea     rdx, ?CounterValue@@3QBGB; "Counter"
0x18002859d  mov     dword ptr [rsp+100h+var_C0.Length], r12d
0x1800285a2  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x1800285a6  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x1800285aa  call    cs:__imp_RtlInitUnicodeString
0x1800285b0  lea     rdx, [rbp+37h+DestinationString]; SourceString
0x1800285b4  lea     rcx, [rsp+100h+var_C0]; DestinationString
0x1800285b9  call    cs:__imp_RtlCopyUnicodeString
0x1800285bf  movzx   edx, [rsp+100h+var_C0.Length]
0x1800285c4  movzx   eax, [rsp+100h+var_C0.MaximumLength]
0x1800285c9  lea     rcx, [rdx+2]
0x1800285cd  cmp     rcx, rax
0x1800285d0  jbe     loc_1800287E0
0x1800285d6  mov     [rsp+100h+var_C8], r12; unsigned int *
0x1800285db  lea     rax, [rbp+37h+arg_8]
0x1800285df  mov     [rsp+100h+var_D0], rax; unsigned int *
0x1800285e4  lea     r8, [rbp+37h+DestinationString]; struct _UNICODE_STRING *
0x1800285e8  mov     [rsp+100h+var_D8], r12; unsigned __int8 *
0x1800285ed  lea     rdx, stru_180067610; struct _UNICODE_STRING *
0x1800285f4  xor     r9d, r9d; unsigned int *
0x1800285f7  mov     [rsp+100h+LengthNeeded], r12; unsigned int *
0x1800285fc  mov     rcx, r15; HKEY
0x1800285ff  call    ?PerfRegQueryValueEx@@YAJPEAUHKEY__@@PEBU_UNICODE_STRING@@1PEAK2PEAE22@Z; PerfRegQueryValueEx(HKEY__ *,_UNICODE_STRING const *,_UNICODE_STRING const *,ulong *,ulong *,uchar *,ulong *,ulong *)
0x180028604  mov     ebx, eax
0x180028606  test    eax, eax
0x180028608  jnz     loc_180028810
0x18002860e  xorps   xmm0, xmm0
0x180028611  mov     [rsp+100h+var_C0.Length], r12w
0x180028617  lea     rdx, ?HelpValue@@3QBGB; "Help"
0x18002861e  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x180028622  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x180028626  call    cs:__imp_RtlInitUnicodeString
0x18002862c  lea     rdx, [rbp+37h+DestinationString]; SourceString
0x180028630  lea     rcx, [rsp+100h+var_C0]; DestinationString
0x180028635  call    cs:__imp_RtlCopyUnicodeString
0x18002863b  movzx   r8d, [rsp+100h+var_C0.Length]
0x180028641  movzx   eax, [rsp+100h+var_C0.MaximumLength]
0x180028646  lea     rcx, [r8+2]
0x18002864a  cmp     rcx, rax
0x18002864d  jbe     loc_1800287F8
0x180028653  mov     [rsp+100h+var_C8], r12; unsigned int *
0x180028658  lea     rax, [rbp+37h+arg_0]
0x18002865c  mov     [rsp+100h+var_D0], rax; unsigned int *
0x180028661  lea     r8, [rbp+37h+DestinationString]; struct _UNICODE_STRING *
0x180028665  mov     [rsp+100h+var_D8], r12; unsigned __int8 *
0x18002866a  lea     rdx, stru_180067610; struct _UNICODE_STRING *
0x180028671  xor     r9d, r9d; unsigned int *
0x180028674  mov     [rsp+100h+LengthNeeded], r12; unsigned int *
0x180028679  mov     rcx, r15; HKEY
0x18002867c  call    ?PerfRegQueryValueEx@@YAJPEAUHKEY__@@PEBU_UNICODE_STRING@@1PEAK2PEAE22@Z; PerfRegQueryValueEx(HKEY__ *,_UNICODE_STRING const *,_UNICODE_STRING const *,ulong *,ulong *,uchar *,ulong *,ulong *)
0x180028681  mov     ebx, eax
0x180028683  test    eax, eax
0x180028685  jnz     loc_180028810
0x18002868b  mov     eax, [rbp+37h+arg_8]
0x18002868e  cmp     [rbp+37h+arg_0], eax
0x180028691  jbe     short loc_180028699
0x180028693  mov     eax, [rbp+37h+arg_0]
0x180028696  mov     [rbp+37h+arg_8], eax
0x180028699  mov     [rdi], eax
0x18002869b  lea     rdx, ?PerflibKey@@3QBGB; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x1800286a2  mov     esi, 1
0x1800286a7  lea     rcx, [rbp+37h+var_70]; DestinationString
0x1800286ab  call    cs:__imp_RtlInitUnicodeString
0x1800286b1  lea     rax, [rbp+37h+var_70]
0x1800286b5  mov     [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x1800286bc  xorps   xmm0, xmm0
0x1800286bf  mov     [rbp+37h+ObjectAttributes.ObjectName], rax
0x1800286c3  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x1800286c7  mov     [rbp+37h+ObjectAttributes.RootDirectory], r12
0x1800286cb  mov     edx, 3000000h; DesiredAccess
0x1800286d0  mov     [rbp+37h+ObjectAttributes.Attributes], 40h ; '@'
0x1800286d7  lea     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x1800286db  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800286e0  call    cs:__imp_NtOpenKey
0x1800286e6  test    eax, eax
0x1800286e8  js      short loc_180028754
0x1800286ea  mov     rdi, [rbp+37h+arg_48]
0x1800286f1  lea     r8, [rbp+37h+SecurityDescriptor]; SecurityDescriptor
0x1800286f5  mov     rcx, [rbp+37h+KeyHandle]; Handle
0x1800286f9  xor     r9d, r9d; Length
0x1800286fc  mov     [rsp+100h+LengthNeeded], rdi; LengthNeeded
0x180028701  mov     [rdi], r12d
0x180028704  lea     edx, [r9+7]
0x180028708  test    esi, esi
0x18002870a  jz      short loc_180028710
0x18002870c  lea     edx, [r9+0Fh]; SecurityInformation
0x180028710  call    cs:__imp_NtQuerySecurityObject
0x180028716  mov     ebx, eax
0x180028718  cmp     eax, 0C0000023h
0x18002871d  jnz     loc_1800287D8
0x180028723  mov     ebx, r12d
0x180028726  mov     rcx, [rbp+37h+KeyHandle]; Handle
0x18002872a  call    cs:__imp_NtClose
0x180028730  test    ebx, ebx
0x180028732  js      short loc_18002879F
0x180028734  mov     ebx, r12d
0x180028737  mov     eax, ebx
0x180028739  mov     rbx, [rsp+100h+arg_10]
0x180028741  add     rsp, 0D0h
0x180028748  pop     r15
0x18002874a  pop     r14
0x18002874c  pop     r13
0x18002874e  pop     r12
0x180028750  pop     rdi
0x180028751  pop     rsi
0x180028752  pop     rbp
0x180028753  retn
0x180028754  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x180028758  mov     edx, 2000000h; DesiredAccess
0x18002875d  lea     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x180028761  call    cs:__imp_NtOpenKey
0x180028767  mov     ebx, eax
0x180028769  mov     esi, r12d
0x18002876c  test    eax, eax
0x18002876e  jns     loc_1800286EA
0x180028774  mov     rcx, cs:WPP_GLOBAL_Control
0x18002877b  test    [rcx+1Ch], r13b
0x18002877f  jz      short loc_1800287CA
0x180028781  cmp     [rcx+19h], r13b
0x180028785  jb      short loc_1800287A6
0x180028787  mov     rcx, [rcx+10h]
0x18002878b  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180028792  mov     edx, 2Eh ; '.'
0x180028797  mov     r9d, eax
0x18002879a  call    WPP_SF_d
0x18002879f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287a6  test    [rcx+1Ch], r13b
0x1800287aa  jz      short loc_1800287CA
0x1800287ac  cmp     [rcx+19h], r13b
0x1800287b0  jb      short loc_1800287CA
0x1800287b2  mov     rcx, [rcx+10h]
0x1800287b6  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x1800287bd  mov     edx, 2Fh ; '/'
0x1800287c2  mov     r9d, ebx
0x1800287c5  call    WPP_SF_d
0x1800287ca  mov     ecx, ebx; int
0x1800287cc  call    ?PerfpDosError@@YAKJ@Z; PerfpDosError(long)
0x1800287d1  mov     ebx, eax
0x1800287d3  jmp     loc_180028737
0x1800287d8  mov     [rdi], r12d
0x1800287db  jmp     loc_180028726
0x1800287e0  mov     rax, [rsp+100h+var_C0.Buffer]
0x1800287e5  shr     rdx, 1
0x1800287e8  mov     [rax+rdx*2], r12w
0x1800287ed  add     [rsp+100h+var_C0.Length], r13w
0x1800287f3  jmp     loc_1800285D6
0x1800287f8  mov     rax, [rsp+100h+var_C0.Buffer]
0x1800287fd  shr     r8, 1
0x180028800  mov     [rax+r8*2], r12w
0x180028805  add     [rsp+100h+var_C0.Length], r13w
0x18002880b  jmp     loc_180028653
0x180028810  mov     rcx, cs:WPP_GLOBAL_Control
0x180028817  test    [rcx+1Ch], r13b
0x18002881b  jz      short loc_18002883B
0x18002881d  cmp     [rcx+19h], r13b
0x180028821  jb      short loc_18002883B
0x180028823  mov     rcx, [rcx+10h]
0x180028827  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x18002882e  mov     edx, 2Dh ; '-'
0x180028833  mov     r9d, ebx
0x180028836  call    WPP_SF_d
0x18002883b  mov     [rsi], r12d
0x18002883e  mov     [r14], r12d
0x180028841  jmp     loc_180028737
```
