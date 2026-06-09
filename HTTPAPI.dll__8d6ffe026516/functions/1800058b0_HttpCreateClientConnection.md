# HttpCreateClientConnection

- ea: `0x1800058b0`
- end: `0x180005aa0`
- name: `HttpCreateClientConnection`
- size: `496`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, int, int, int, int, int, __int64, int, int, int, char, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180002b40`
- `0x1800058b0`
- `0x18000a4c8`
- `0x18000b080`
- `0x18000b0b8`
- `0x18000ba5c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180005a08`
- `ntdll!RtlNtStatusToDosError` at `0x180005a08`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800059fc`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800059fc`

## pseudocode

```c
__int64 __fastcall HttpCreateClientConnection(
        HANDLE FileHandle,
        __int64 a2,
        const WCHAR *a3,
        __int16 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        __int64 a10,
        int a11,
        int a12,
        int a13,
        char a14,
        _QWORD *a15)
{
  int v19; // edx
  int v20; // ecx
  int v21; // r8d
  ULONG v22; // ebx
  int inited; // eax
  __int64 v24; // rcx
  __int64 v25; // r9
  __int64 v27; // [rsp+90h] [rbp-61h] BYREF
  __int64 v28; // [rsp+98h] [rbp-59h] BYREF
  __int64 InputBuffer; // [rsp+A0h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-49h] BYREF
  __int16 v31; // [rsp+B8h] [rbp-39h]
  int v32; // [rsp+BCh] [rbp-35h]
  int v33; // [rsp+C0h] [rbp-31h]
  int v34; // [rsp+C4h] [rbp-2Dh]
  int v35; // [rsp+C8h] [rbp-29h]
  int v36; // [rsp+CCh] [rbp-25h]
  int v37; // [rsp+D0h] [rbp-21h]
  int v38; // [rsp+D4h] [rbp-1Dh]
  __int64 v39; // [rsp+D8h] [rbp-19h]
  int v40; // [rsp+E0h] [rbp-11h]
  char v41; // [rsp+E4h] [rbp-Dh]

  memset_0(&InputBuffer, 0, 0x48u);
  v28 = 0;
  LODWORD(v27) = 0;
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_qISdLLLLDqLDLDq(
      v20,
      v19,
      v21,
      (_DWORD)FileHandle,
      a2,
      (__int64)a3,
      a4,
      a5,
      a6,
      a7,
      a8,
      a9,
      a10,
      a11,
      a12,
      a13,
      a14,
      a15,
      v27);
  if ( a15 && (*a15 = 0, a3) )
  {
    v33 = a5;
    v34 = a6;
    v35 = a7;
    v36 = a8;
    v37 = a9;
    v39 = a10;
    v40 = a11;
    v38 = a12;
    InputBuffer = a2;
    v31 = a4;
    v32 = a13;
    v41 = a14;
    inited = RtlInitUnicodeStringEx(&DestinationString, a3);
    if ( inited >= 0 )
    {
      v22 = HttpApiSynchronousDeviceControl(FileHandle, 0x1240B4u, &InputBuffer, 0x48u, &v28, 8u, (__int64)&v27);
      if ( !v22 )
      {
        v25 = v28;
        *a15 = v28;
        if ( (byte_1800126A3 & 4) == 0 )
          return v22;
        WPP_SF_I(v24, 27, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids, v25);
      }
    }
    else
    {
      v22 = RtlNtStatusToDosError(inited);
    }
  }
  else
  {
    v22 = 87;
  }
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_d(1050, 28, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids, v22);
  return v22;
}

```

## disassembly

```asm
0x1800058b0  push    rbp
0x1800058b2  push    rbx
0x1800058b3  push    rsi
0x1800058b4  push    rdi
0x1800058b5  push    r12
0x1800058b7  push    r13
0x1800058b9  push    r14
0x1800058bb  push    r15
0x1800058bd  lea     rbp, [rsp-7]
0x1800058c2  sub     rsp, 0F8h
0x1800058c9  mov     r15, rdx
0x1800058cc  movzx   r14d, r9w
0x1800058d0  xor     edx, edx; Val
0x1800058d2  mov     rbx, r8
0x1800058d5  mov     rsi, rcx
0x1800058d8  lea     rcx, [rbp+3Fh+InputBuffer]; void *
0x1800058dc  lea     r8d, [rdx+48h]; Size
0x1800058e0  call    memset_0
0x1800058e5  mov     [rbp+3Fh+var_98], 0
0x1800058ed  mov     dword ptr [rbp+3Fh+var_A0], 0
0x1800058f4  test    cs:byte_1800126A3, 4
0x1800058fb  mov     rdi, [rbp+3Fh+arg_70]
0x180005902  movzx   r12d, [rbp+3Fh+arg_68]
0x18000590a  mov     r13d, [rbp+3Fh+arg_60]
0x180005911  jz      short loc_180005988
0x180005913  mov     eax, [rbp+3Fh+arg_58]
0x180005919  mov     r9, rsi
0x18000591c  mov     [rsp+130h+var_A8], rdi
0x180005924  mov     [rsp+130h+var_B0], r12d
0x18000592c  mov     [rsp+130h+var_B8], r13d
0x180005931  mov     [rsp+130h+var_C0], eax
0x180005935  mov     eax, [rbp+3Fh+arg_50]
0x18000593b  mov     [rsp+130h+var_C8], eax
0x18000593f  mov     rax, [rbp+3Fh+arg_48]
0x180005946  mov     [rsp+130h+var_D0], rax
0x18000594b  mov     eax, [rbp+3Fh+arg_40]
0x180005951  mov     [rsp+130h+var_D8], eax
0x180005955  mov     eax, [rbp+3Fh+arg_38]
0x18000595b  mov     [rsp+130h+var_E0], eax
0x18000595f  mov     eax, [rbp+3Fh+arg_30]
0x180005962  mov     [rsp+130h+var_E8], eax
0x180005966  mov     eax, [rbp+3Fh+arg_28]
0x180005969  mov     [rsp+130h+var_F0], eax
0x18000596d  mov     eax, [rbp+3Fh+arg_20]
0x180005970  mov     [rsp+130h+var_F8], eax
0x180005974  mov     dword ptr [rsp+130h+var_100], r14d
0x180005979  mov     qword ptr [rsp+130h+var_108], rbx
0x18000597e  mov     [rsp+130h+var_110], r15
0x180005983  call    WPP_SF_qISdLLLLDqLDLDq
0x180005988  test    rdi, rdi
0x18000598b  jnz     short loc_180005997
0x18000598d  mov     ebx, 57h ; 'W'
0x180005992  jmp     loc_180005A68
0x180005997  mov     qword ptr [rdi], 0
0x18000599e  test    rbx, rbx
0x1800059a1  jz      short loc_18000598D
0x1800059a3  mov     eax, [rbp+3Fh+arg_20]
0x1800059a6  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x1800059aa  mov     [rbp+3Fh+var_70], eax
0x1800059ad  mov     rdx, rbx; SourceString
0x1800059b0  mov     eax, [rbp+3Fh+arg_28]
0x1800059b3  mov     [rbp+3Fh+var_6C], eax
0x1800059b6  mov     eax, [rbp+3Fh+arg_30]
0x1800059b9  mov     [rbp+3Fh+var_68], eax
0x1800059bc  mov     eax, [rbp+3Fh+arg_38]
0x1800059c2  mov     [rbp+3Fh+var_64], eax
0x1800059c5  mov     eax, [rbp+3Fh+arg_40]
0x1800059cb  mov     [rbp+3Fh+var_60], eax
0x1800059ce  mov     rax, [rbp+3Fh+arg_48]
0x1800059d5  mov     [rbp+3Fh+var_58], rax
0x1800059d9  mov     eax, [rbp+3Fh+arg_50]
0x1800059df  mov     [rbp+3Fh+var_50], eax
0x1800059e2  mov     eax, [rbp+3Fh+arg_58]
0x1800059e8  mov     [rbp+3Fh+var_5C], eax
0x1800059eb  mov     [rbp+3Fh+InputBuffer], r15
0x1800059ef  mov     [rbp+3Fh+var_78], r14w
0x1800059f4  mov     [rbp+3Fh+var_74], r13d
0x1800059f8  mov     [rbp+3Fh+var_4C], r12b
0x1800059fc  call    cs:__imp_RtlInitUnicodeStringEx
0x180005a02  test    eax, eax
0x180005a04  jns     short loc_180005A12
0x180005a06  mov     ecx, eax; Status
0x180005a08  call    cs:__imp_RtlNtStatusToDosError
0x180005a0e  mov     ebx, eax
0x180005a10  jmp     short loc_180005A68
0x180005a12  lea     rax, [rbp+3Fh+var_A0]
0x180005a16  mov     r9d, 48h ; 'H'; InputBufferLength
0x180005a1c  mov     [rsp+130h+var_100], rax; __int64
0x180005a21  lea     r8, [rbp+3Fh+InputBuffer]; InputBuffer
0x180005a25  lea     rax, [rbp+3Fh+var_98]
0x180005a29  mov     [rsp+130h+var_108], 8; ULONG
0x180005a31  mov     edx, 1240B4h; IoControlCode
0x180005a36  mov     [rsp+130h+var_110], rax; PVOID
0x180005a3b  mov     rcx, rsi; FileHandle
0x180005a3e  call    HttpApiSynchronousDeviceControl
0x180005a43  mov     ebx, eax
0x180005a45  test    eax, eax
0x180005a47  jnz     short loc_180005A68
0x180005a49  mov     r9, [rbp+3Fh+var_98]
0x180005a4d  mov     [rdi], r9
0x180005a50  test    cs:byte_1800126A3, 4
0x180005a57  jz      short loc_180005A8A
0x180005a59  lea     edx, [rax+1Bh]
0x180005a5c  lea     r8, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids
0x180005a63  call    WPP_SF_I
0x180005a68  test    cs:byte_1800126A3, 4
0x180005a6f  jz      short loc_180005A8A
0x180005a71  mov     edx, 1Ch
0x180005a76  lea     r8, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids
0x180005a7d  mov     ecx, 41Ah
0x180005a82  mov     r9d, ebx
0x180005a85  call    WPP_SF_d
0x180005a8a  mov     eax, ebx
0x180005a8c  add     rsp, 0F8h
0x180005a93  pop     r15
0x180005a95  pop     r14
0x180005a97  pop     r13
0x180005a99  pop     r12
0x180005a9b  pop     rdi
0x180005a9c  pop     rsi
0x180005a9d  pop     rbx
0x180005a9e  pop     rbp
0x180005a9f  retn
```
