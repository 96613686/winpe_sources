# CFspCloudFileSystemOperations::GetSecurity(void *,ulong,void * *)

- ea: `0x180099e00`
- end: `0x180099fb0`
- name: `?GetSecurity@CFspCloudFileSystemOperations@@SAJPEAXKPEAPEAX@Z`
- size: `432`
- prototype: `__int64 __fastcall(HANDLE Handle, unsigned int, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800950b4`

## callees

- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x180090c60`
- `0x1800984c8`
- `0x180099e00`

## import_xrefs

- `ntdll!NtQuerySecurityObject` at `0x180099eec`
- `ntdll!NtQuerySecurityObject` at `0x180099f59`
- `ntdll!NtQuerySecurityObject` at `0x180099eec`
- `ntdll!NtQuerySecurityObject` at `0x180099f59`

## string_xrefs

- `0x180099e7c`: `CFspCloudFileSystemOperations::GetSecurity`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFspCloudFileSystemOperations::GetSecurity(HANDLE Handle, __int64 a2, void **a3)
{
  _DWORD *v5; // rax
  char v6; // cl
  __int16 v7; // ax
  int v8; // ebx
  bool v9; // zf
  PSECURITY_DESCRIPTOR v10; // rdi
  __int16 v11; // ax
  unsigned int v12; // eax
  ULONG Length; // [rsp+30h] [rbp-30h] BYREF
  int v15; // [rsp+38h] [rbp-28h] BYREF
  int v16; // [rsp+3Ch] [rbp-24h]
  char v17; // [rsp+40h] [rbp-20h]
  const char *v18; // [rsp+48h] [rbp-18h]
  __int64 v19; // [rsp+50h] [rbp-10h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+80h] [rbp+20h] BYREF

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, WPP_e0db9af3e7d6384a3fbe331b6c49ab76_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
  }
  if ( (v5[17] & 0x100) != 0 && *((_BYTE *)v5 + 65) >= 6u )
  {
    v6 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v6 = 0;
LABEL_9:
  v15 = 0;
  v16 = 983;
  v17 = v6;
  v18 = "CFspCloudFileSystemOperations::GetSecurity";
  v19 = 0;
  SecurityDescriptor = 0;
  Length = 0;
  if ( a3 )
    *a3 = 0;
  v7 = 990;
  if ( !Handle )
  {
    v8 = -2147024809;
LABEL_13:
    v15 = v8;
    HIWORD(v16) = v7;
    goto LABEL_22;
  }
  v15 = 0;
  LOWORD(v16) = 990;
  v9 = NtQuerySecurityObject(Handle, 4u, 0, 0, &Length) == -1073741789;
  v7 = 998;
  if ( !v9 )
  {
    v8 = -2147418113;
    goto LABEL_13;
  }
  v15 = 0;
  LOWORD(v16) = 998;
  v8 = EcsAlloc(Length, &SecurityDescriptor);
  v15 = v8;
  v10 = SecurityDescriptor;
  v11 = 1002;
  if ( v8 < 0
    || (LOWORD(v16) = 1002,
        v12 = NtQuerySecurityObject(Handle, 4u, SecurityDescriptor, Length, &Length),
        v8 = HRESULTFromNTSTATUS(v12),
        v15 = v8,
        v11 = 1008,
        v8 < 0) )
  {
    HIWORD(v16) = v11;
  }
  else
  {
    LOWORD(v16) = 1008;
    *a3 = v10;
    v10 = 0;
  }
  if ( v10 )
  {
    EcsFree(v10);
    v8 = v15;
  }
LABEL_22:
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v15);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180099e00  mov     [rsp-18h+arg_8], rbx
0x180099e05  mov     [rsp-18h+arg_10], rsi
0x180099e0a  push    rbp
0x180099e0b  push    rdi
0x180099e0c  push    r14
0x180099e0e  mov     rbp, rsp
0x180099e11  sub     rsp, 60h
0x180099e15  mov     rsi, r8
0x180099e18  mov     r14, rcx
0x180099e1b  lea     rcx, WPP_GLOBAL_Control
0x180099e22  mov     ebx, 100h
0x180099e27  mov     rax, cs:WPP_GLOBAL_Control
0x180099e2e  cmp     rax, rcx
0x180099e31  jz      short loc_180099E5A
0x180099e33  test    [rax+44h], ebx
0x180099e36  jz      short loc_180099E69
0x180099e38  cmp     byte ptr [rax+41h], 6
0x180099e3c  jb      short loc_180099E5A
0x180099e3e  mov     edx, 1Ch
0x180099e43  lea     r8, WPP_e0db9af3e7d6384a3fbe331b6c49ab76_Traceguids
0x180099e4a  mov     rcx, [rax+38h]
0x180099e4e  call    WPP_SF_
0x180099e53  mov     rax, cs:WPP_GLOBAL_Control
0x180099e5a  test    [rax+44h], ebx
0x180099e5d  jz      short loc_180099E69
0x180099e5f  cmp     byte ptr [rax+41h], 6
0x180099e63  jb      short loc_180099E69
0x180099e65  mov     cl, 1
0x180099e67  jmp     short loc_180099E6B
0x180099e69  xor     cl, cl
0x180099e6b  mov     [rbp+var_28], 0
0x180099e72  mov     [rbp+var_24], 3D7h
0x180099e79  mov     [rbp+var_20], cl
0x180099e7c  lea     rax, aCfspcloudfiles_5; "CFspCloudFileSystemOperations::GetSecur"...
0x180099e83  mov     [rbp+var_18], rax
0x180099e87  mov     [rbp+var_10], 0
0x180099e8f  mov     [rbp+SecurityDescriptor], 0
0x180099e97  mov     [rbp+Length], 0
0x180099e9e  test    rsi, rsi
0x180099ea1  jz      short loc_180099EAA
0x180099ea3  mov     qword ptr [rsi], 0
0x180099eaa  mov     eax, [rbp+var_28]
0x180099ead  mov     [rbp+var_28], eax
0x180099eb0  mov     eax, 3DEh
0x180099eb5  test    r14, r14
0x180099eb8  jnz     short loc_180099ECB
0x180099eba  mov     ebx, 80070057h
0x180099ebf  mov     [rbp+var_28], ebx
0x180099ec2  mov     word ptr [rbp+var_24+2], ax
0x180099ec6  jmp     loc_180099F90
0x180099ecb  mov     [rbp+var_28], 0
0x180099ed2  mov     word ptr [rbp+var_24], ax
0x180099ed6  lea     rax, [rbp+Length]
0x180099eda  mov     [rsp+60h+LengthNeeded], rax; LengthNeeded
0x180099edf  xor     r9d, r9d; Length
0x180099ee2  xor     r8d, r8d; SecurityDescriptor
0x180099ee5  lea     edx, [r9+4]; SecurityInformation
0x180099ee9  mov     rcx, r14; Handle
0x180099eec  call    cs:__imp_NtQuerySecurityObject
0x180099ef2  mov     ecx, [rbp+var_28]
0x180099ef5  mov     [rbp+var_28], ecx
0x180099ef8  cmp     eax, 0C0000023h
0x180099efd  mov     eax, 3E6h
0x180099f02  jz      short loc_180099F0B
0x180099f04  mov     ebx, 8000FFFFh
0x180099f09  jmp     short loc_180099EBF
0x180099f0b  mov     [rbp+var_28], 0
0x180099f12  mov     word ptr [rbp+var_24], ax
0x180099f16  mov     ecx, [rbp+Length]; unsigned __int64
0x180099f19  lea     rdx, [rbp+SecurityDescriptor]; void **
0x180099f1d  call    ?EcsAlloc@@YAJ_KPEAPEAX@Z; EcsAlloc(unsigned __int64,void * *)
0x180099f22  mov     ebx, eax
0x180099f24  mov     [rbp+var_28], eax
0x180099f27  mov     [rbp+var_28], eax
0x180099f2a  mov     rdi, [rbp+SecurityDescriptor]
0x180099f2e  test    eax, eax
0x180099f30  mov     eax, 3EAh
0x180099f35  jns     short loc_180099F3D
0x180099f37  mov     word ptr [rbp+var_24+2], ax
0x180099f3b  jmp     short loc_180099F80
0x180099f3d  mov     word ptr [rbp+var_24], ax
0x180099f41  lea     rax, [rbp+Length]
0x180099f45  mov     [rsp+60h+LengthNeeded], rax; LengthNeeded
0x180099f4a  mov     r9d, [rbp+Length]; Length
0x180099f4e  mov     r8, rdi; SecurityDescriptor
0x180099f51  mov     edx, 4; SecurityInformation
0x180099f56  mov     rcx, r14; Handle
0x180099f59  call    cs:__imp_NtQuerySecurityObject
0x180099f5f  mov     ecx, eax
0x180099f61  call    HRESULTFromNTSTATUS
0x180099f66  mov     ebx, eax
0x180099f68  mov     [rbp+var_28], eax
0x180099f6b  mov     [rbp+var_28], eax
0x180099f6e  test    eax, eax
0x180099f70  mov     eax, 3F0h
0x180099f75  js      short loc_180099F37
0x180099f77  mov     word ptr [rbp+var_24], ax
0x180099f7b  mov     [rsi], rdi
0x180099f7e  xor     edi, edi
0x180099f80  test    rdi, rdi
0x180099f83  jz      short loc_180099F90
0x180099f85  mov     rcx, rdi; void *
0x180099f88  call    ?EcsFree@@YAJPEAX@Z; EcsFree(void *)
0x180099f8d  mov     ebx, [rbp+var_28]
0x180099f90  lea     rcx, [rbp+var_28]; this
0x180099f94  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180099f99  mov     eax, ebx
0x180099f9b  lea     r11, [rsp+60h+var_s0]
0x180099fa0  mov     rbx, [r11+28h]
0x180099fa4  mov     rsi, [r11+30h]
0x180099fa8  mov     rsp, r11
0x180099fab  pop     r14
0x180099fad  pop     rdi
0x180099fae  pop     rbp
0x180099faf  retn
```
