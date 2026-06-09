# SensorGroup::CreateSensorGroupAttributes(IMFAttributes * *)

- ea: `0x18004b110`
- end: `0x18004b1e6`
- name: `?CreateSensorGroupAttributes@SensorGroup@@UEAAJPEAPEAUIMFAttributes@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(SensorGroup *__hidden this, struct IMFAttributes **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005fa0`
- `0x18004b110`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b1d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b1d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b128`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b128`
- `MFPlat!MFCreateAttributes` at `0x18004b16a`
- `MFPlat!MFCreateAttributes` at `0x18004b16a`

## pseudocode

```c
__int64 __fastcall SensorGroup::CreateSensorGroupAttributes(SensorGroup *this, struct IMFAttributes **a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  unsigned int v5; // ebx
  char *v6; // rsi
  IMFAttributes **v7; // rdi
  HRESULT v8; // eax
  __int64 v9; // rdx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( a2 )
  {
    v6 = (char *)this - 8;
    v7 = (IMFAttributes **)((char *)this + 64);
    if ( *((_QWORD *)v6 + 9) || (v8 = MFCreateAttributes(v7, 1u), v5 = v8, v8 >= 0) )
    {
      v8 = ((__int64 (__fastcall *)(IMFAttributes *, GUID *, struct IMFAttributes **))(*v7)->lpVtbl->QueryInterface)(
             *v7,
             &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3,
             a2);
      v5 = v8;
      if ( v8 >= 0 || !g_wppLevels )
        goto LABEL_12;
      v9 = 60;
    }
    else
    {
      if ( !g_wppLevels )
        goto LABEL_12;
      v9 = 59;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, v6, v8);
    goto LABEL_12;
  }
  v5 = -2147467261;
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      58,
      &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
      (char *)this - 8,
      -2147467261);
LABEL_12:
  LeaveCriticalSection(v2);
  return v5;
}

```

## disassembly

```asm
0x18004b110  push    rbx
0x18004b112  push    rbp
0x18004b113  push    rsi
0x18004b114  push    rdi
0x18004b115  push    r14
0x18004b117  sub     rsp, 30h
0x18004b11b  lea     rbp, [rcx+18h]
0x18004b11f  mov     rdi, rcx
0x18004b122  mov     rcx, rbp; lpCriticalSection
0x18004b125  mov     r14, rdx
0x18004b128  call    cs:__imp_EnterCriticalSection
0x18004b12e  test    r14, r14
0x18004b131  jnz     short loc_18004B153
0x18004b133  mov     ebx, 80004003h
0x18004b138  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b13f  jb      loc_18004B1D0
0x18004b145  lea     r9, [rdi-8]
0x18004b149  mov     [rsp+58h+var_38], ebx
0x18004b14d  lea     edx, [r14+3Ah]
0x18004b151  jmp     short loc_18004B1B9
0x18004b153  lea     rsi, [rdi-8]
0x18004b157  add     rdi, 40h ; '@'
0x18004b15b  cmp     qword ptr [rsi+48h], 0
0x18004b160  jnz     short loc_18004B186
0x18004b162  mov     edx, 1; cInitialSize
0x18004b167  mov     rcx, rdi; ppMFAttributes
0x18004b16a  call    cs:__imp_MFCreateAttributes
0x18004b170  mov     ebx, eax
0x18004b172  test    eax, eax
0x18004b174  jns     short loc_18004B186
0x18004b176  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b17d  jb      short loc_18004B1D0
0x18004b17f  mov     edx, 3Bh ; ';'
0x18004b184  jmp     short loc_18004B1B2
0x18004b186  mov     rcx, [rdi]
0x18004b189  lea     rdx, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x18004b190  mov     r8, r14
0x18004b193  mov     rax, [rcx]
0x18004b196  mov     rax, [rax]
0x18004b199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b19e  mov     ebx, eax
0x18004b1a0  test    eax, eax
0x18004b1a2  jns     short loc_18004B1D0
0x18004b1a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b1ab  jb      short loc_18004B1D0
0x18004b1ad  mov     edx, 3Ch ; '<'
0x18004b1b2  mov     r9, rsi
0x18004b1b5  mov     [rsp+58h+var_38], eax
0x18004b1b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b1c0  lea     r8, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x18004b1c7  mov     rcx, [rcx+10h]
0x18004b1cb  call    WPP_SF_qD
0x18004b1d0  mov     rcx, rbp; lpCriticalSection
0x18004b1d3  call    cs:__imp_LeaveCriticalSection
0x18004b1d9  mov     eax, ebx
0x18004b1db  add     rsp, 30h
0x18004b1df  pop     r14
0x18004b1e1  pop     rdi
0x18004b1e2  pop     rsi
0x18004b1e3  pop     rbp
0x18004b1e4  pop     rbx
0x18004b1e5  retn
```
