# ShieldProvider::GetPersistedKey(ushort const *,ushort const *,ushort * *)

- ea: `0x14000c110`
- end: `0x14000c253`
- name: `?GetPersistedKey@ShieldProvider@@YAJPEBG0PEAPEAG@Z`
- size: `323`
- prototype: `__int64 __fastcall(ShieldProvider *this, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140003188`

## callees

- `0x140001614`
- `0x140003040`
- `0x14000c110`
- `0x14000ebf8`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x14000c159`
- `ntdll!RtlGetPersistedStateLocation` at `0x14000c1fa`
- `ntdll!RtlGetPersistedStateLocation` at `0x14000c159`
- `ntdll!RtlGetPersistedStateLocation` at `0x14000c1fa`
- `ntdll!RtlNtStatusToDosError` at `0x14000c202`
- `ntdll!RtlNtStatusToDosError` at `0x14000c202`

## string_xrefs

- `0x14000c140`: `SOFTWARE\Microsoft\Windows Security Health\Miscellaneous`
- `0x14000c1de`: `SOFTWARE\Microsoft\Windows Security Health\Miscellaneous`
- `0x14000c14b`: `Windows Security Health`
- `0x14000c1e9`: `Windows Security Health`

## pseudocode

```c
__int64 __fastcall ShieldProvider::GetPersistedKey(
        ShieldProvider *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  void *v4; // rbx
  NTSTATUS PersistedStateLocation; // eax
  unsigned __int64 v7; // r8
  unsigned int v8; // edi
  int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  signed int v12; // eax
  void *v14; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v15; // [rsp+58h] [rbp+10h] BYREF
  int v16; // [rsp+5Ch] [rbp+14h]

  v16 = HIDWORD(a2);
  v4 = 0;
  v14 = 0;
  v15 = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"Windows Security Health",
                             0,
                             L"SOFTWARE\\Microsoft\\Windows Security Health\\Miscellaneous",
                             0,
                             0,
                             0,
                             &v15);
  if ( PersistedStateLocation == -2147483643 )
  {
    if ( v15 < 2uLL )
    {
      v8 = -2147024809;
LABEL_5:
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 26;
LABEL_8:
        WPP_SF_d(v10[2], v11, WPP_33a0f43f06d933957ab6919b163618ef_Traceguids, v8);
        goto LABEL_9;
      }
      goto LABEL_9;
    }
    v9 = CommonUtil::MpNewAlloc((CommonUtil *)&v14, (void **)v15, v7);
    v4 = v14;
    v8 = v9;
    if ( v9 < 0 )
      goto LABEL_5;
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"Windows Security Health",
                               0,
                               L"SOFTWARE\\Microsoft\\Windows Security Health\\Miscellaneous",
                               0,
                               v14,
                               v15,
                               &v15);
  }
  v12 = RtlNtStatusToDosError(PersistedStateLocation);
  v8 = v12;
  if ( v12 > 0 )
    v8 = (unsigned __int16)v12 | 0x80070000;
  if ( (v8 & 0x80000000) == 0 )
  {
    *(_QWORD *)a3 = v4;
    return v8;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 27;
    goto LABEL_8;
  }
LABEL_9:
  if ( v4 )
    operator delete(v4);
  return v8;
}

```

## disassembly

```asm
0x14000c110  mov     rax, rsp
0x14000c113  mov     [rax+18h], rbx
0x14000c117  mov     [rax+20h], rsi
0x14000c11b  mov     [rax+10h], rdx
0x14000c11f  mov     [rax+8], rcx
0x14000c123  push    rdi
0x14000c124  sub     rsp, 40h
0x14000c128  xor     ebx, ebx
0x14000c12a  mov     rsi, r8
0x14000c12d  mov     [rax+8], rbx
0x14000c131  xor     r9d, r9d
0x14000c134  mov     [rax+10h], ebx
0x14000c137  lea     rax, [rax+10h]
0x14000c13b  mov     [rsp+48h+var_18], rax
0x14000c140  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Security H"...
0x14000c147  mov     [rsp+48h+var_20], ebx
0x14000c14b  lea     rcx, aWindowsSecurit; "Windows Security Health"
0x14000c152  xor     edx, edx
0x14000c154  mov     [rsp+48h+var_28], rbx
0x14000c159  call    cs:__imp_RtlGetPersistedStateLocation
0x14000c15f  cmp     eax, 80000005h
0x14000c164  jnz     loc_14000C200
0x14000c16a  mov     edx, dword ptr [rsp+48h+arg_8]; void **
0x14000c16e  cmp     rdx, 2
0x14000c172  jnb     short loc_14000C17B
0x14000c174  mov     edi, 80070057h
0x14000c179  jmp     short loc_14000C190
0x14000c17b  lea     rcx, [rsp+48h+arg_0]; this
0x14000c180  call    ?MpNewAlloc@CommonUtil@@YAJPEAPEAX_K@Z; CommonUtil::MpNewAlloc(void * *,unsigned __int64)
0x14000c185  mov     rbx, [rsp+48h+arg_0]
0x14000c18a  mov     edi, eax
0x14000c18c  test    eax, eax
0x14000c18e  jns     short loc_14000C1D0
0x14000c190  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c197  lea     rax, WPP_GLOBAL_Control
0x14000c19e  cmp     rcx, rax
0x14000c1a1  jz      short loc_14000C1C1
0x14000c1a3  test    byte ptr [rcx+1Ch], 1
0x14000c1a7  jz      short loc_14000C1C1
0x14000c1a9  mov     edx, 1Ah
0x14000c1ae  mov     rcx, [rcx+10h]
0x14000c1b2  lea     r8, WPP_33a0f43f06d933957ab6919b163618ef_Traceguids
0x14000c1b9  mov     r9d, edi
0x14000c1bc  call    WPP_SF_d
0x14000c1c1  test    rbx, rbx
0x14000c1c4  jz      short loc_14000C241
0x14000c1c6  mov     rcx, rbx; void *
0x14000c1c9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000c1ce  jmp     short loc_14000C241
0x14000c1d0  mov     eax, dword ptr [rsp+48h+arg_8]
0x14000c1d4  lea     rdx, [rsp+48h+arg_8]
0x14000c1d9  mov     [rsp+48h+var_18], rdx
0x14000c1de  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Security H"...
0x14000c1e5  mov     [rsp+48h+var_20], eax
0x14000c1e9  lea     rcx, aWindowsSecurit; "Windows Security Health"
0x14000c1f0  xor     edx, edx
0x14000c1f2  mov     [rsp+48h+var_28], rbx
0x14000c1f7  xor     r9d, r9d
0x14000c1fa  call    cs:__imp_RtlGetPersistedStateLocation
0x14000c200  mov     ecx, eax; Status
0x14000c202  call    cs:__imp_RtlNtStatusToDosError
0x14000c208  mov     edi, eax
0x14000c20a  test    eax, eax
0x14000c20c  jle     short loc_14000C217
0x14000c20e  movzx   edi, ax
0x14000c211  or      edi, 80070000h
0x14000c217  test    edi, edi
0x14000c219  jns     short loc_14000C23E
0x14000c21b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c222  lea     rax, WPP_GLOBAL_Control
0x14000c229  cmp     rcx, rax
0x14000c22c  jz      short loc_14000C1C1
0x14000c22e  test    byte ptr [rcx+1Ch], 1
0x14000c232  jz      short loc_14000C1C1
0x14000c234  mov     edx, 1Bh
0x14000c239  jmp     loc_14000C1AE
0x14000c23e  mov     [rsi], rbx
0x14000c241  mov     rbx, [rsp+48h+arg_10]
0x14000c246  mov     eax, edi
0x14000c248  mov     rsi, [rsp+48h+arg_18]
0x14000c24d  add     rsp, 40h
0x14000c251  pop     rdi
0x14000c252  retn
```
