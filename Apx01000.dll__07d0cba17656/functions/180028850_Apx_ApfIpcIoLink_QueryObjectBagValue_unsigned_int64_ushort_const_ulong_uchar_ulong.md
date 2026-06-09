# Apx::ApfIpcIoLink::QueryObjectBagValue(unsigned __int64,ushort const *,ulong,uchar *,ulong *)

- ea: `0x180028850`
- end: `0x180028b03`
- name: `?QueryObjectBagValue@ApfIpcIoLink@Apx@@UEAAJ_KPEBGKPEAEPEAK@Z`
- size: `691`
- prototype: `__int64 __fastcall(unsigned __int64 this, __int64, const unsigned __int16 *, int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x180001d30`
- `0x180002100`
- `0x18000213c`
- `0x1800027c8`
- `0x18000ba84`
- `0x180011e6c`
- `0x180028850`
- `0x18002956c`
- `0x180029880`

## pseudocode

```c
__int64 __fastcall Apx::ApfIpcIoLink::QueryObjectBagValue(
        unsigned __int64 this,
        __int64 a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int8 *a5,
        unsigned int *a6)
{
  int v8; // r15d
  DWORD v9; // ebp
  __int64 v10; // r8
  unsigned int *v11; // rax
  __int64 v12; // r8
  unsigned int *v13; // rsi
  unsigned int v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rdx
  char *v17; // rax
  char *v18; // rcx
  const struct std::nothrow_t *v19; // rdx
  DWORD NumberOfBytesTransferred; // [rsp+54h] [rbp-294h] BYREF
  __int64 v23; // [rsp+58h] [rbp-290h]
  _QWORD *v24; // [rsp+60h] [rbp-288h]
  _QWORD v25[2]; // [rsp+70h] [rbp-278h] BYREF
  int v26; // [rsp+80h] [rbp-268h]
  int v27; // [rsp+84h] [rbp-264h]
  int v28; // [rsp+88h] [rbp-260h]
  char v29; // [rsp+8Ch] [rbp-25Ch] BYREF

  v23 = a2;
  NumberOfBytesTransferred = 0;
  v8 = 0;
  v9 = 8;
  memset_0(v25, 0, 0x228u);
  if ( !a6 || (v10 = *a6, !(_DWORD)v10) || !a5 )
  {
LABEL_6:
    v11 = (unsigned int *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
    v13 = v11;
    if ( !v11 )
    {
      v14 = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_qidd(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, v12, ~this, *(_QWORD *)(this + 64), v9, -2147024882);
      }
      return v14;
    }
    memset_0(v11, 0, v9);
    v26 = v8;
    v24 = (_QWORD *)(this + 64);
    v15 = 2147483646;
    v16 = 260;
    v25[0] = *(_QWORD *)(this + 64);
    v25[1] = v23;
    v27 = a4;
    v28 = *a6;
    v17 = &v29;
    do
    {
      if ( !v15 )
        break;
      if ( !*a3 )
        break;
      *(_WORD *)v17 = *a3++;
      v17 += 2;
      --v15;
      --v16;
    }
    while ( v16 );
    v18 = v17 - 2;
    if ( v16 )
      v18 = v17;
    *(_WORD *)v18 = 0;
    v14 = Apx::ApfHelper::SyncIoctl(
            *(void **)(this + 112),
            0x1388u,
            0x1DC084u,
            v25,
            0x228u,
            v13,
            v9,
            &NumberOfBytesTransferred,
            0);
    if ( (v14 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_qqd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids,
          ~this,
          *v24,
          v14);
      }
      goto LABEL_32;
    }
    if ( v8 )
    {
      if ( *v13 > *a6 )
      {
        v14 = -805306139;
LABEL_32:
        operator delete(v13, v19);
        return v14;
      }
      memcpy_0(a5, v13 + 1, *v13);
    }
    v14 = 0;
    *a6 = *v13;
    goto LABEL_32;
  }
  if ( (unsigned int)(v10 + 8) >= 8 )
  {
    v9 = v10 + 8;
    v8 = 1;
    goto LABEL_6;
  }
  v14 = -2147024362;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_qidd(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, v10, ~this, *(_QWORD *)(this + 64), v10, -2147024362);
  }
  return v14;
}

```

## disassembly

```asm
0x180028850  mov     [rsp+arg_10], rbx
0x180028855  push    rbp
0x180028856  push    rsi
0x180028857  push    rdi
0x180028858  push    r12
0x18002885a  push    r13
0x18002885c  push    r14
0x18002885e  push    r15
0x180028860  sub     rsp, 2B0h
0x180028867  mov     rax, cs:__security_cookie
0x18002886e  xor     rax, rsp
0x180028871  mov     [rsp+2E8h+var_48], rax
0x180028879  mov     r13, [rsp+2E8h+arg_20]
0x180028881  xor     ebx, ebx
0x180028883  mov     r14, [rsp+2E8h+arg_28]
0x18002888b  mov     r12, r8
0x18002888e  mov     [rsp+2E8h+var_290], rdx
0x180028893  mov     rdi, rcx
0x180028896  xor     edx, edx; Val
0x180028898  mov     [rsp+2E8h+var_298], r9d
0x18002889d  mov     r8d, 228h; Size
0x1800288a3  mov     [rsp+2E8h+NumberOfBytesTransferred], ebx
0x1800288a7  lea     rcx, [rsp+2E8h+var_278]; void *
0x1800288ac  mov     r15d, ebx
0x1800288af  lea     ebp, [rbx+8]
0x1800288b2  call    memset_0
0x1800288b7  test    r14, r14
0x1800288ba  jz      short loc_1800288D7
0x1800288bc  mov     r8d, [r14]
0x1800288bf  test    r8d, r8d
0x1800288c2  jz      short loc_1800288D7
0x1800288c4  test    r13, r13
0x1800288c7  jz      short loc_1800288D7
0x1800288c9  lea     eax, [r8+8]
0x1800288cd  cmp     eax, ebp
0x1800288cf  jb      short loc_180028930
0x1800288d1  mov     ebp, eax
0x1800288d3  lea     r15d, [rbx+1]
0x1800288d7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800288de  mov     ecx, ebp; unsigned __int64
0x1800288e0  mov     ebx, ebp
0x1800288e2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800288e7  mov     rsi, rax
0x1800288ea  test    rax, rax
0x1800288ed  jnz     loc_18002898B
0x1800288f3  mov     ebx, 8007000Eh
0x1800288f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800288ff  lea     rax, WPP_GLOBAL_Control
0x180028906  cmp     rcx, rax
0x180028909  jz      loc_180028AD6
0x18002890f  test    byte ptr [rcx+1Ch], 80h
0x180028913  jz      loc_180028AD6
0x180028919  cmp     byte ptr [rcx+19h], 2
0x18002891d  jb      loc_180028AD6
0x180028923  mov     [rsp+2E8h+var_2B8], ebx
0x180028927  lea     edx, [rsi+23h]
0x18002892a  mov     dword ptr [rsp+2E8h+var_2C0], ebp
0x18002892e  jmp     short loc_18002896E
0x180028930  mov     ebx, 80070216h
0x180028935  mov     rcx, cs:WPP_GLOBAL_Control
0x18002893c  lea     rax, WPP_GLOBAL_Control
0x180028943  cmp     rcx, rax
0x180028946  jz      loc_180028AD6
0x18002894c  test    byte ptr [rcx+1Ch], 80h
0x180028950  jz      loc_180028AD6
0x180028956  cmp     byte ptr [rcx+19h], 2
0x18002895a  jb      loc_180028AD6
0x180028960  mov     [rsp+2E8h+var_2B8], ebx
0x180028964  mov     edx, 22h ; '"'
0x180028969  mov     dword ptr [rsp+2E8h+var_2C0], r8d
0x18002896e  mov     rax, [rdi+40h]
0x180028972  mov     r9, rdi
0x180028975  mov     rcx, [rcx+10h]
0x180028979  not     r9
0x18002897c  mov     qword ptr [rsp+2E8h+nInBufferSize], rax
0x180028981  call    WPP_SF_qidd
0x180028986  jmp     loc_180028AD6
0x18002898b  mov     r8, rbx; Size
0x18002898e  xor     edx, edx; Val
0x180028990  mov     rcx, rsi; void *
0x180028993  call    memset_0
0x180028998  lea     rax, [rdi+40h]
0x18002899c  mov     [rsp+2E8h+var_268], r15d
0x1800289a4  mov     [rsp+2E8h+var_288], rax
0x1800289a9  mov     ecx, 7FFFFFFEh
0x1800289ae  mov     rax, [rax]
0x1800289b1  mov     edx, 104h
0x1800289b6  mov     [rsp+2E8h+var_278], rax
0x1800289bb  xor     r9d, r9d
0x1800289be  mov     rax, [rsp+2E8h+var_290]
0x1800289c3  mov     [rsp+2E8h+var_270], rax
0x1800289c8  mov     eax, [rsp+2E8h+var_298]
0x1800289cc  mov     [rsp+2E8h+var_264], eax
0x1800289d3  mov     eax, [r14]
0x1800289d6  mov     [rsp+2E8h+var_260], eax
0x1800289dd  lea     rax, [rsp+2E8h+var_25C]
0x1800289e5  test    rcx, rcx
0x1800289e8  jz      short loc_180028A0A
0x1800289ea  movzx   r8d, word ptr [r12]
0x1800289ef  test    r8w, r8w
0x1800289f3  jz      short loc_180028A0A
0x1800289f5  mov     [rax], r8w
0x1800289f9  add     r12, 2
0x1800289fd  add     rax, 2
0x180028a01  dec     rcx
0x180028a04  sub     rdx, 1
0x180028a08  jnz     short loc_1800289E5
0x180028a0a  mov     [rsp+2E8h+var_2A8], r9; void *
0x180028a0f  lea     rcx, [rax-2]
0x180028a13  test    rdx, rdx
0x180028a16  mov     r8d, 1DC084h; unsigned int
0x180028a1c  mov     edx, 1388h; unsigned int
0x180028a21  cmovnz  rcx, rax
0x180028a25  lea     rax, [rsp+2E8h+NumberOfBytesTransferred]
0x180028a2a  mov     [rsp+2E8h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180028a2f  mov     [rsp+2E8h+var_2B8], ebp; DWORD
0x180028a33  mov     [rsp+2E8h+var_2C0], rsi; void *
0x180028a38  mov     [rcx], r9w
0x180028a3c  lea     r9, [rsp+2E8h+var_278]; void *
0x180028a41  mov     rcx, [rdi+70h]; void *
0x180028a45  mov     [rsp+2E8h+nInBufferSize], 228h; nInBufferSize
0x180028a4d  call    ?SyncIoctl@ApfHelper@Apx@@SAJPEAXKK0K0KPEAK0@Z; Apx::ApfHelper::SyncIoctl(void *,ulong,ulong,void *,ulong,void *,ulong,ulong *,void *)
0x180028a52  xor     ebp, ebp
0x180028a54  mov     ebx, eax
0x180028a56  test    eax, eax
0x180028a58  jns     short loc_180028AA5
0x180028a5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a61  lea     rax, WPP_GLOBAL_Control
0x180028a68  cmp     rcx, rax
0x180028a6b  jz      short loc_180028ACE
0x180028a6d  test    byte ptr [rcx+1Ch], 80h
0x180028a71  jz      short loc_180028ACE
0x180028a73  cmp     byte ptr [rcx+19h], 3
0x180028a77  jb      short loc_180028ACE
0x180028a79  mov     rax, [rsp+2E8h+var_288]
0x180028a7e  lea     edx, [rbp+24h]
0x180028a81  mov     rcx, [rcx+10h]
0x180028a85  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180028a8c  not     rdi
0x180028a8f  mov     dword ptr [rsp+2E8h+var_2C0], ebx
0x180028a93  mov     r9, rdi
0x180028a96  mov     rax, [rax]
0x180028a99  mov     qword ptr [rsp+2E8h+nInBufferSize], rax
0x180028a9e  call    WPP_SF_qqd
0x180028aa3  jmp     short loc_180028ACE
0x180028aa5  test    r15d, r15d
0x180028aa8  jz      short loc_180028AC7
0x180028aaa  mov     eax, [rsi]
0x180028aac  cmp     eax, [r14]
0x180028aaf  jbe     short loc_180028AB8
0x180028ab1  mov     ebx, 0D00000E5h
0x180028ab6  jmp     short loc_180028ACE
0x180028ab8  mov     r8, rax; Size
0x180028abb  lea     rdx, [rsi+4]; Src
0x180028abf  mov     rcx, r13; void *
0x180028ac2  call    memcpy_0
0x180028ac7  mov     eax, [rsi]
0x180028ac9  mov     ebx, ebp
0x180028acb  mov     [r14], eax
0x180028ace  mov     rcx, rsi; void *
0x180028ad1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028ad6  mov     eax, ebx
0x180028ad8  mov     rcx, [rsp+2E8h+var_48]
0x180028ae0  xor     rcx, rsp; StackCookie
0x180028ae3  call    __security_check_cookie
0x180028ae8  mov     rbx, [rsp+2E8h+arg_10]
0x180028af0  add     rsp, 2B0h
0x180028af7  pop     r15
0x180028af9  pop     r14
0x180028afb  pop     r13
0x180028afd  pop     r12
0x180028aff  pop     rdi
0x180028b00  pop     rsi
0x180028b01  pop     rbp
0x180028b02  retn
```
