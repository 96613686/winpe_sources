# PerfRegQueryInfoKey

- ea: `0x18002ae50`
- end: `0x18002b223`
- name: `PerfRegQueryInfoKey`
- size: `979`
- prototype: `__int64 __usercall@<rax>(HKEY@<rcx>, __int64, __int64, __int64, __int64, __int64, PULONG, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180029698`
- `0x18002ae50`
- `0x18002b280`
- `0x18003fb18`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18002b0a4`
- `ntdll!NtOpenKey` at `0x18002b138`
- `ntdll!NtOpenKey` at `0x18002b0a4`
- `ntdll!NtOpenKey` at `0x18002b138`
- `ntdll!NtClose` at `0x18002b0fa`
- `ntdll!NtClose` at `0x18002b0fa`
- `ntdll!RtlCopyUnicodeString` at `0x18002af65`
- `ntdll!RtlCopyUnicodeString` at `0x18002afed`
- `ntdll!RtlCopyUnicodeString` at `0x18002af65`
- `ntdll!RtlCopyUnicodeString` at `0x18002afed`
- `ntdll!NtQuerySecurityObject` at `0x18002b0da`
- `ntdll!NtQuerySecurityObject` at `0x18002b0da`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18002aec1`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18002aec1`
- `ntdll!RtlInitUnicodeString` at `0x18002af50`
- `ntdll!RtlInitUnicodeString` at `0x18002afd8`
- `ntdll!RtlInitUnicodeString` at `0x18002b069`
- `ntdll!RtlInitUnicodeString` at `0x18002af50`
- `ntdll!RtlInitUnicodeString` at `0x18002afd8`
- `ntdll!RtlInitUnicodeString` at `0x18002b069`

## string_xrefs

- `0x18002b059`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Perflib`

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
  RtlRunOnceExecuteOnce(qword_1800B21D0, PerfpInitializeCallback, 0, 0);
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
    v20 = PerfRegQueryValueEx(a1, &stru_1800755F0, &DestinationString, 0, 0, 0, &v38, 0);
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
    v20 = PerfRegQueryValueEx(a1, &stru_1800755F0, &DestinationString, 0, 0, 0, &v37, 0);
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
0x18002ae50  mov     [rsp-8+arg_10], rbx
0x18002ae55  push    rbp
0x18002ae56  push    rsi
0x18002ae57  push    rdi
0x18002ae58  push    r12
0x18002ae5a  push    r13
0x18002ae5c  push    r14
0x18002ae5e  push    r15
0x18002ae60  lea     rbp, [rsp-7]
0x18002ae65  sub     rsp, 0D0h
0x18002ae6c  xorps   xmm0, xmm0
0x18002ae6f  xor     r12d, r12d
0x18002ae72  xorps   xmm1, xmm1
0x18002ae75  mov     [rbp+37h+arg_0], r12d
0x18002ae79  mov     rdi, r9
0x18002ae7c  mov     [rbp+37h+arg_8], r12d
0x18002ae80  mov     rbx, rdx
0x18002ae83  mov     [rbp+37h+KeyHandle], r12
0x18002ae87  mov     r15, rcx
0x18002ae8a  lea     rdx, PerfpInitializeCallback
0x18002ae91  xor     eax, eax
0x18002ae93  lea     rcx, qword_1800B21D0
0x18002ae9a  xor     r9d, r9d
0x18002ae9d  mov     [rbp+37h+var_40], rax
0x18002aea1  xor     r8d, r8d
0x18002aea4  movups  xmmword ptr [rsp+100h+var_C0.Length], xmm0
0x18002aea9  movups  [rbp+37h+SecurityDescriptor], xmm1
0x18002aead  movups  [rbp+37h+var_50], xmm1
0x18002aeb1  movups  xmmword ptr [rbp+37h+ObjectAttributes.Length], xmm0
0x18002aeb5  movups  xmmword ptr [rbp+37h+ObjectAttributes.ObjectName], xmm0
0x18002aeb9  movups  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002aebd  movups  xmmword ptr [rbp+37h+var_70.Length], xmm0
0x18002aec1  call    cs:__imp_RtlRunOnceExecuteOnce
0x18002aec8  nop     dword ptr [rax+rax+00h]
0x18002aecd  lea     r13d, [r12+2]
0x18002aed2  cmp     [rbx+2], r13w
0x18002aed7  jb      short loc_18002AEE5
0x18002aed9  mov     rcx, [rbx+8]
0x18002aedd  mov     [rbx], r12w
0x18002aee1  mov     [rcx], r12w
0x18002aee5  mov     rax, [rbp+37h+arg_20]
0x18002aee9  mov     rsi, [rbp+37h+arg_30]
0x18002aeed  mov     r14, [rbp+37h+arg_38]
0x18002aef1  mov     [rdi], r12d
0x18002aef4  mov     rdi, [rbp+37h+arg_40]
0x18002aefb  mov     [rax], r12d
0x18002aefe  mov     rax, [rbp+37h+arg_28]
0x18002af02  mov     [rax], r12d
0x18002af05  mov     rax, [rbp+37h+arg_50]
0x18002af0c  mov     [rsi], r13d
0x18002af0f  mov     dword ptr [r14], 1Eh
0x18002af16  mov     [rdi], r12d
0x18002af19  test    rax, rax
0x18002af1c  jz      short loc_18002AF21
0x18002af1e  mov     [rax], r12
0x18002af21  lea     rax, [r15+7FFFFFB0h]
0x18002af28  test    rax, 0FFFFFFFFFFFFFFEFh
0x18002af2e  jnz     loc_18002B059
0x18002af34  xorps   xmm0, xmm0
0x18002af37  mov     [rsp+100h+var_C0.Buffer], r12
0x18002af3c  lea     rdx, ?CounterValue@@3QBGB; "Counter"
0x18002af43  mov     dword ptr [rsp+100h+var_C0.Length], r12d
0x18002af48  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x18002af4c  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x18002af50  call    cs:__imp_RtlInitUnicodeString
0x18002af57  nop     dword ptr [rax+rax+00h]
0x18002af5c  lea     rdx, [rbp+37h+DestinationString]; SourceString
0x18002af60  lea     rcx, [rsp+100h+var_C0]; DestinationString
0x18002af65  call    cs:__imp_RtlCopyUnicodeString
0x18002af6c  nop     dword ptr [rax+rax+00h]
0x18002af71  movzx   edx, [rsp+100h+var_C0.Length]
0x18002af76  movzx   eax, [rsp+100h+var_C0.MaximumLength]
0x18002af7b  lea     rcx, [rdx+2]
0x18002af7f  cmp     rcx, rax
0x18002af82  jbe     loc_18002B1BD
0x18002af88  mov     [rsp+100h+var_C8], r12; unsigned int *
0x18002af8d  lea     rax, [rbp+37h+arg_8]
0x18002af91  mov     [rsp+100h+var_D0], rax; unsigned int *
0x18002af96  lea     r8, [rbp+37h+DestinationString]; struct _UNICODE_STRING *
0x18002af9a  mov     [rsp+100h+var_D8], r12; unsigned __int8 *
0x18002af9f  lea     rdx, stru_1800755F0; struct _UNICODE_STRING *
0x18002afa6  xor     r9d, r9d; unsigned int *
0x18002afa9  mov     [rsp+100h+LengthNeeded], r12; unsigned int *
0x18002afae  mov     rcx, r15; HKEY
0x18002afb1  call    ?PerfRegQueryValueEx@@YAJPEAUHKEY__@@PEBU_UNICODE_STRING@@1PEAK2PEAE22@Z; PerfRegQueryValueEx(HKEY__ *,_UNICODE_STRING const *,_UNICODE_STRING const *,ulong *,ulong *,uchar *,ulong *,ulong *)
0x18002afb6  mov     ebx, eax
0x18002afb8  test    eax, eax
0x18002afba  jnz     loc_18002B1ED
0x18002afc0  xorps   xmm0, xmm0
0x18002afc3  mov     [rsp+100h+var_C0.Length], r12w
0x18002afc9  lea     rdx, ?HelpValue@@3QBGB; "Help"
0x18002afd0  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x18002afd4  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x18002afd8  call    cs:__imp_RtlInitUnicodeString
0x18002afdf  nop     dword ptr [rax+rax+00h]
0x18002afe4  lea     rdx, [rbp+37h+DestinationString]; SourceString
0x18002afe8  lea     rcx, [rsp+100h+var_C0]; DestinationString
0x18002afed  call    cs:__imp_RtlCopyUnicodeString
0x18002aff4  nop     dword ptr [rax+rax+00h]
0x18002aff9  movzx   r8d, [rsp+100h+var_C0.Length]
0x18002afff  movzx   eax, [rsp+100h+var_C0.MaximumLength]
0x18002b004  lea     rcx, [r8+2]
0x18002b008  cmp     rcx, rax
0x18002b00b  jbe     loc_18002B1D5
0x18002b011  mov     [rsp+100h+var_C8], r12; unsigned int *
0x18002b016  lea     rax, [rbp+37h+arg_0]
0x18002b01a  mov     [rsp+100h+var_D0], rax; unsigned int *
0x18002b01f  lea     r8, [rbp+37h+DestinationString]; struct _UNICODE_STRING *
0x18002b023  mov     [rsp+100h+var_D8], r12; unsigned __int8 *
0x18002b028  lea     rdx, stru_1800755F0; struct _UNICODE_STRING *
0x18002b02f  xor     r9d, r9d; unsigned int *
0x18002b032  mov     [rsp+100h+LengthNeeded], r12; unsigned int *
0x18002b037  mov     rcx, r15; HKEY
0x18002b03a  call    ?PerfRegQueryValueEx@@YAJPEAUHKEY__@@PEBU_UNICODE_STRING@@1PEAK2PEAE22@Z; PerfRegQueryValueEx(HKEY__ *,_UNICODE_STRING const *,_UNICODE_STRING const *,ulong *,ulong *,uchar *,ulong *,ulong *)
0x18002b03f  mov     ebx, eax
0x18002b041  test    eax, eax
0x18002b043  jnz     loc_18002B1ED
0x18002b049  mov     eax, [rbp+37h+arg_8]
0x18002b04c  cmp     [rbp+37h+arg_0], eax
0x18002b04f  jbe     short loc_18002B057
0x18002b051  mov     eax, [rbp+37h+arg_0]
0x18002b054  mov     [rbp+37h+arg_8], eax
0x18002b057  mov     [rdi], eax
0x18002b059  lea     rdx, ?PerflibKey@@3QBGB; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18002b060  mov     esi, 1
0x18002b065  lea     rcx, [rbp+37h+var_70]; DestinationString
0x18002b069  call    cs:__imp_RtlInitUnicodeString
0x18002b070  nop     dword ptr [rax+rax+00h]
0x18002b075  lea     rax, [rbp+37h+var_70]
0x18002b079  mov     [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x18002b080  xorps   xmm0, xmm0
0x18002b083  mov     [rbp+37h+ObjectAttributes.ObjectName], rax
0x18002b087  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x18002b08b  mov     [rbp+37h+ObjectAttributes.RootDirectory], r12
0x18002b08f  mov     edx, 3000000h; DesiredAccess
0x18002b094  mov     [rbp+37h+ObjectAttributes.Attributes], 40h ; '@'
0x18002b09b  lea     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x18002b09f  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002b0a4  call    cs:__imp_NtOpenKey
0x18002b0ab  nop     dword ptr [rax+rax+00h]
0x18002b0b0  test    eax, eax
0x18002b0b2  js      short loc_18002B12B
0x18002b0b4  mov     rdi, [rbp+37h+arg_48]
0x18002b0bb  lea     r8, [rbp+37h+SecurityDescriptor]; SecurityDescriptor
0x18002b0bf  mov     rcx, [rbp+37h+KeyHandle]; Handle
0x18002b0c3  xor     r9d, r9d; Length
0x18002b0c6  mov     [rsp+100h+LengthNeeded], rdi; LengthNeeded
0x18002b0cb  mov     [rdi], r12d
0x18002b0ce  lea     edx, [r9+7]
0x18002b0d2  test    esi, esi
0x18002b0d4  jz      short loc_18002B0DA
0x18002b0d6  lea     edx, [r9+0Fh]; SecurityInformation
0x18002b0da  call    cs:__imp_NtQuerySecurityObject
0x18002b0e1  nop     dword ptr [rax+rax+00h]
0x18002b0e6  mov     ebx, eax
0x18002b0e8  cmp     eax, 0C0000023h
0x18002b0ed  jnz     loc_18002B1B5
0x18002b0f3  mov     ebx, r12d
0x18002b0f6  mov     rcx, [rbp+37h+KeyHandle]; Handle
0x18002b0fa  call    cs:__imp_NtClose
0x18002b101  nop     dword ptr [rax+rax+00h]
0x18002b106  test    ebx, ebx
0x18002b108  js      short loc_18002B17C
0x18002b10a  mov     ebx, r12d
0x18002b10d  mov     eax, ebx
0x18002b10f  mov     rbx, [rsp+100h+arg_10]
0x18002b117  add     rsp, 0D0h
0x18002b11e  pop     r15
0x18002b120  pop     r14
0x18002b122  pop     r13
0x18002b124  pop     r12
0x18002b126  pop     rdi
0x18002b127  pop     rsi
0x18002b128  pop     rbp
0x18002b129  retn
0x18002b12b  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x18002b12f  mov     edx, 2000000h; DesiredAccess
0x18002b134  lea     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x18002b138  call    cs:__imp_NtOpenKey
0x18002b13f  nop     dword ptr [rax+rax+00h]
0x18002b144  mov     ebx, eax
0x18002b146  mov     esi, r12d
0x18002b149  test    eax, eax
0x18002b14b  jns     loc_18002B0B4
0x18002b151  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b158  test    [rcx+1Ch], r13b
0x18002b15c  jz      short loc_18002B1A7
0x18002b15e  cmp     [rcx+19h], r13b
0x18002b162  jb      short loc_18002B183
0x18002b164  mov     rcx, [rcx+10h]
0x18002b168  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x18002b16f  mov     edx, 2Eh ; '.'
0x18002b174  mov     r9d, eax
0x18002b177  call    WPP_SF_d
0x18002b17c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b183  test    [rcx+1Ch], r13b
0x18002b187  jz      short loc_18002B1A7
0x18002b189  cmp     [rcx+19h], r13b
0x18002b18d  jb      short loc_18002B1A7
0x18002b18f  mov     rcx, [rcx+10h]
0x18002b193  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x18002b19a  mov     edx, 2Fh ; '/'
0x18002b19f  mov     r9d, ebx
0x18002b1a2  call    WPP_SF_d
0x18002b1a7  mov     ecx, ebx; int
0x18002b1a9  call    ?PerfpDosError@@YAKJ@Z; PerfpDosError(long)
0x18002b1ae  mov     ebx, eax
0x18002b1b0  jmp     loc_18002B10D
0x18002b1b5  mov     [rdi], r12d
0x18002b1b8  jmp     loc_18002B0F6
0x18002b1bd  mov     rax, [rsp+100h+var_C0.Buffer]
0x18002b1c2  shr     rdx, 1
0x18002b1c5  mov     [rax+rdx*2], r12w
0x18002b1ca  add     [rsp+100h+var_C0.Length], r13w
0x18002b1d0  jmp     loc_18002AF88
0x18002b1d5  mov     rax, [rsp+100h+var_C0.Buffer]
0x18002b1da  shr     r8, 1
0x18002b1dd  mov     [rax+r8*2], r12w
0x18002b1e2  add     [rsp+100h+var_C0.Length], r13w
0x18002b1e8  jmp     loc_18002B011
0x18002b1ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1f4  test    [rcx+1Ch], r13b
0x18002b1f8  jz      short loc_18002B218
0x18002b1fa  cmp     [rcx+19h], r13b
0x18002b1fe  jb      short loc_18002B218
0x18002b200  mov     rcx, [rcx+10h]
0x18002b204  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x18002b20b  mov     edx, 2Dh ; '-'
0x18002b210  mov     r9d, ebx
0x18002b213  call    WPP_SF_d
0x18002b218  mov     [rsi], r12d
0x18002b21b  mov     [r14], r12d
0x18002b21e  jmp     loc_18002B10D
```
