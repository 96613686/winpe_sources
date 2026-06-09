# SxIsBootVolume(ushort const *)

- ea: `0x140006334`
- end: `0x14000651c`
- name: `?SxIsBootVolume@@YAJPEBG@Z`
- size: `488`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x140002670`
- `0x1400029b4`
- `0x1400050f0`

## callees

- `0x1400054f4`
- `0x140006018`
- `0x140006334`
- `0x140006cc8`
- `0x14000e324`
- `0x14000e41c`
- `0x14001094e`
- `0x140010980`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000644a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000644a`
- `msvcrt!_wcsicmp` at `0x1400064c9`
- `msvcrt!_wcsicmp` at `0x1400064c9`

## pseudocode

```c
__int64 __fastcall SxIsBootVolume(const unsigned __int16 *a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int16 v4; // ax
  int UniqueVolumeForPath; // ebx
  DWORD v6; // ecx
  int v8; // [rsp+20h] [rbp-E0h] BYREF
  __int16 v9; // [rsp+24h] [rbp-DCh]
  __int16 v10; // [rsp+26h] [rbp-DAh]
  WCHAR Dst[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t String2[264]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t String1[264]; // [rsp+480h] [rbp+380h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, a1);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "SxIsBootVolume", 812, 1);
  memset_0(Dst, 0, 0x20Au);
  memset_0(String1, 0, 0x20Au);
  memset_0(String2, 0, 0x20Au);
  v4 = 819;
  if ( !a1 )
  {
    UniqueVolumeForPath = -2147024809;
LABEL_6:
    v8 = UniqueVolumeForPath;
LABEL_7:
    v10 = v4;
    goto LABEL_17;
  }
  v8 = 0;
  v9 = 819;
  UniqueVolumeForPath = SxGetUniqueVolumeForPath(a1, String2);
  v8 = UniqueVolumeForPath;
  v4 = 824;
  if ( UniqueVolumeForPath < 0 )
    goto LABEL_7;
  v9 = 824;
  v6 = ExpandEnvironmentStringsW(L"%SystemDrive%\\", Dst, 0x105u);
  if ( !v6 )
  {
    UniqueVolumeForPath = GetLastFailureAsHRESULT();
    v8 = UniqueVolumeForPath;
    v4 = 833;
    goto LABEL_7;
  }
  v9 = 833;
  v4 = 834;
  if ( v6 > 0x105 )
  {
    UniqueVolumeForPath = -2147024774;
    goto LABEL_6;
  }
  v8 = 0;
  v9 = 834;
  UniqueVolumeForPath = SxGetUniqueVolumeForPath(Dst, String1);
  v8 = UniqueVolumeForPath;
  v4 = 836;
  if ( UniqueVolumeForPath < 0 )
    goto LABEL_7;
  v9 = 836;
  if ( _wcsicmp(String1, String2) )
  {
    UniqueVolumeForPath = 1;
    v8 = 1;
    v9 = 840;
  }
  else
  {
    UniqueVolumeForPath = v8;
  }
LABEL_17:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8, v2, v3);
  return (unsigned int)UniqueVolumeForPath;
}

```

## disassembly

```asm
0x140006334  mov     [rsp-8+arg_8], rbx
0x140006339  mov     [rsp-8+arg_10], rdi
0x14000633e  push    rbp
0x14000633f  lea     rbp, [rsp-5A0h]
0x140006347  sub     rsp, 6A0h
0x14000634e  mov     rax, cs:__security_cookie
0x140006355  xor     rax, rsp
0x140006358  mov     [rbp+5A0h+var_10], rax
0x14000635f  mov     rbx, rcx
0x140006362  mov     rcx, cs:WPP_GLOBAL_Control
0x140006369  lea     rax, WPP_GLOBAL_Control
0x140006370  cmp     rcx, rax
0x140006373  jz      short loc_140006396
0x140006375  test    dword ptr [rcx+1Ch], 20000000h
0x14000637c  jz      short loc_140006396
0x14000637e  mov     rcx, [rcx+10h]
0x140006382  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x140006389  mov     edx, 18h
0x14000638e  mov     r9, rbx
0x140006391  call    WPP_SF_S
0x140006396  mov     r9d, 1; unsigned __int16
0x14000639c  lea     rdx, aSxisbootvolume; "SxIsBootVolume"
0x1400063a3  mov     r8d, 32Ch; unsigned __int16
0x1400063a9  lea     rcx, [rsp+6A0h+var_680]; this
0x1400063ae  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1400063b3  mov     edi, 20Ah
0x1400063b8  lea     rcx, [rsp+6A0h+Dst]; void *
0x1400063bd  mov     r8d, edi; Size
0x1400063c0  xor     edx, edx; Val
0x1400063c2  call    memset_0
0x1400063c7  mov     r8d, edi; Size
0x1400063ca  lea     rcx, [rbp+5A0h+String1]; void *
0x1400063d1  xor     edx, edx; Val
0x1400063d3  call    memset_0
0x1400063d8  mov     r8d, edi; Size
0x1400063db  lea     rcx, [rbp+5A0h+String2]; void *
0x1400063e2  xor     edx, edx; Val
0x1400063e4  call    memset_0
0x1400063e9  mov     eax, 333h
0x1400063ee  test    rbx, rbx
0x1400063f1  jnz     short loc_140006406
0x1400063f3  mov     ebx, 80070057h
0x1400063f8  mov     [rsp+6A0h+var_680], ebx
0x1400063fc  mov     [rsp+6A0h+var_67A], ax
0x140006401  jmp     loc_1400064EC
0x140006406  lea     rdx, [rbp+5A0h+String2]; lpszVolumeName
0x14000640d  mov     [rsp+6A0h+var_680], 0
0x140006415  mov     rcx, rbx; unsigned __int16 *
0x140006418  mov     [rsp+6A0h+var_67C], ax
0x14000641d  call    ?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z; SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)
0x140006422  mov     ebx, eax
0x140006424  mov     [rsp+6A0h+var_680], eax
0x140006428  test    eax, eax
0x14000642a  mov     eax, 338h
0x14000642f  js      short loc_1400063FC
0x140006431  mov     ebx, 105h
0x140006436  mov     [rsp+6A0h+var_67C], ax
0x14000643b  mov     r8d, ebx; nSize
0x14000643e  lea     rdx, [rsp+6A0h+Dst]; lpDst
0x140006443  lea     rcx, Src; "%SystemDrive%\\"
0x14000644a  call    cs:__imp_ExpandEnvironmentStringsW
0x140006450  mov     ecx, eax
0x140006452  test    eax, eax
0x140006454  jnz     short loc_140006468
0x140006456  call    GetLastFailureAsHRESULT
0x14000645b  mov     ebx, eax
0x14000645d  mov     [rsp+6A0h+var_680], eax
0x140006461  mov     eax, 341h
0x140006466  jmp     short loc_1400063FC
0x140006468  mov     eax, 341h
0x14000646d  mov     [rsp+6A0h+var_67C], ax
0x140006472  mov     eax, 342h
0x140006477  cmp     ecx, ebx
0x140006479  jbe     short loc_140006485
0x14000647b  mov     ebx, 8007007Ah
0x140006480  jmp     loc_1400063F8
0x140006485  lea     rdx, [rbp+5A0h+String1]; lpszVolumeName
0x14000648c  mov     [rsp+6A0h+var_680], 0
0x140006494  lea     rcx, [rsp+6A0h+Dst]; unsigned __int16 *
0x140006499  mov     [rsp+6A0h+var_67C], ax
0x14000649e  call    ?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z; SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)
0x1400064a3  mov     ebx, eax
0x1400064a5  mov     [rsp+6A0h+var_680], eax
0x1400064a9  test    eax, eax
0x1400064ab  mov     eax, 344h
0x1400064b0  js      loc_1400063FC
0x1400064b6  lea     rdx, [rbp+5A0h+String2]; String2
0x1400064bd  mov     [rsp+6A0h+var_67C], ax
0x1400064c2  lea     rcx, [rbp+5A0h+String1]; String1
0x1400064c9  call    cs:__imp__wcsicmp
0x1400064cf  test    eax, eax
0x1400064d1  jz      short loc_1400064E8
0x1400064d3  mov     ebx, 1
0x1400064d8  mov     eax, 348h
0x1400064dd  mov     [rsp+6A0h+var_680], ebx
0x1400064e1  mov     [rsp+6A0h+var_67C], ax
0x1400064e6  jmp     short loc_1400064EC
0x1400064e8  mov     ebx, [rsp+6A0h+var_680]
0x1400064ec  lea     rcx, [rsp+6A0h+var_680]; this
0x1400064f1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1400064f6  mov     eax, ebx
0x1400064f8  mov     rcx, [rbp+5A0h+var_10]
0x1400064ff  xor     rcx, rsp; StackCookie
0x140006502  call    __security_check_cookie
0x140006507  lea     r11, [rsp+6A0h+var_s0]
0x14000650f  mov     rbx, [r11+18h]
0x140006513  mov     rdi, [r11+20h]
0x140006517  mov     rsp, r11
0x14000651a  pop     rbp
0x14000651b  retn
```
