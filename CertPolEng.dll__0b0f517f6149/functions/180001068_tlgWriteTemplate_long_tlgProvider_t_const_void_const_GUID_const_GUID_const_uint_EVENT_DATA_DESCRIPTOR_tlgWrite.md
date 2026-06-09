# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001068`
- end: `0x1800011ae`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U2@U2@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@44AEBU?$_tlgWrapperByVal@$03@@6@Z`
- size: `326`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, __int64 *, __int64 **, __int64, __int64 **, __int64 **, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800170fc`

## callees

- `0x180001068`
- `0x180007e00`
- `0x18001a380`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        __int64 **a6,
        __int64 a7,
        __int64 **a8,
        __int64 **a9,
        __int64 a10,
        __int64 a11)
{
  __int64 v13; // rcx
  int v14; // r8d
  __int64 *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  __int64 *v18; // rdx
  __int64 v19; // rax
  int v20; // eax
  __int64 *v21; // rdx
  _BYTE v23[32]; // [rsp+30h] [rbp-81h] BYREF
  __int64 v24; // [rsp+50h] [rbp-61h]
  __int64 v25; // [rsp+58h] [rbp-59h]
  __int64 *v26; // [rsp+60h] [rbp-51h]
  int v27; // [rsp+68h] [rbp-49h]
  int v28; // [rsp+6Ch] [rbp-45h]
  __int64 v29; // [rsp+70h] [rbp-41h]
  __int64 v30; // [rsp+78h] [rbp-39h]
  __int64 *v31; // [rsp+80h] [rbp-31h]
  int v32; // [rsp+88h] [rbp-29h]
  int v33; // [rsp+8Ch] [rbp-25h]
  __int64 *v34; // [rsp+90h] [rbp-21h]
  int v35; // [rsp+98h] [rbp-19h]
  int v36; // [rsp+9Ch] [rbp-15h]
  __int64 v37; // [rsp+A0h] [rbp-11h]
  __int64 v38; // [rsp+A8h] [rbp-9h]
  __int64 v39; // [rsp+B0h] [rbp-1h]
  __int64 v40; // [rsp+B8h] [rbp+7h]

  v39 = a11;
  v37 = a10;
  v13 = -1;
  v14 = 2;
  v40 = 4;
  v38 = 4;
  v15 = *a9;
  if ( *a9 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v15 = &qword_180020CC0;
    v17 = 2;
  }
  v35 = v17;
  v34 = v15;
  v36 = 0;
  v18 = *a8;
  if ( *a8 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)v18 + v19) );
    v20 = 2 * v19 + 2;
  }
  else
  {
    v18 = &qword_180020CC0;
    v20 = 2;
  }
  v32 = v20;
  v29 = a7;
  v31 = v18;
  v33 = 0;
  v30 = 8;
  v21 = *a6;
  if ( *a6 )
  {
    do
      ++v13;
    while ( *((_WORD *)v21 + v13) );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v21 = &qword_180020CC0;
  }
  v27 = v14;
  v26 = v21;
  v28 = 0;
  v24 = *a5;
  v25 = 16;
  return tlgWriteTransfer_EtwEventWriteTransfer(a1, a2, 0, 0, 9, (__int64)v23);
}

```

## disassembly

```asm
0x180001068  push    rbp
0x18000106a  lea     rbp, [rsp-1Fh]
0x18000106f  sub     rsp, 0D0h
0x180001076  mov     rax, cs:__security_cookie
0x18000107d  xor     rax, rsp
0x180001080  mov     [rbp+1Fh+var_10], rax
0x180001084  mov     rax, [rbp+1Fh+arg_50]
0x180001088  xor     r9d, r9d
0x18000108b  mov     [rbp+1Fh+var_20], rax
0x18000108f  mov     r11, rdx
0x180001092  mov     rax, [rbp+1Fh+arg_48]
0x180001096  mov     r10, rcx
0x180001099  mov     [rbp+1Fh+var_30], rax
0x18000109d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800010a1  mov     rax, [rbp+1Fh+arg_40]
0x1800010a5  lea     r8d, [r9+2]
0x1800010a9  mov     [rbp+1Fh+var_18], 4
0x1800010b1  mov     [rbp+1Fh+var_28], 4
0x1800010b9  mov     rdx, [rax]
0x1800010bc  test    rdx, rdx
0x1800010bf  jz      short loc_1800010D7
0x1800010c1  mov     rax, rcx
0x1800010c4  inc     rax
0x1800010c7  cmp     [rdx+rax*2], r9w
0x1800010cc  jnz     short loc_1800010C4
0x1800010ce  lea     eax, ds:2[rax*2]
0x1800010d5  jmp     short loc_1800010E1
0x1800010d7  lea     rdx, qword_180020CC0
0x1800010de  mov     eax, r8d
0x1800010e1  mov     [rbp+1Fh+var_38], eax
0x1800010e4  mov     rax, [rbp+1Fh+arg_38]
0x1800010e8  mov     [rbp+1Fh+var_40], rdx
0x1800010ec  mov     [rbp+1Fh+var_34], r9d
0x1800010f0  mov     rdx, [rax]
0x1800010f3  test    rdx, rdx
0x1800010f6  jz      short loc_18000110E
0x1800010f8  mov     rax, rcx
0x1800010fb  inc     rax
0x1800010fe  cmp     [rdx+rax*2], r9w
0x180001103  jnz     short loc_1800010FB
0x180001105  lea     eax, ds:2[rax*2]
0x18000110c  jmp     short loc_180001118
0x18000110e  lea     rdx, qword_180020CC0
0x180001115  mov     eax, r8d
0x180001118  mov     [rbp+1Fh+var_48], eax
0x18000111b  mov     rax, [rbp+1Fh+arg_30]
0x18000111f  mov     [rbp+1Fh+var_60], rax
0x180001123  mov     rax, [rbp+1Fh+arg_28]
0x180001127  mov     [rbp+1Fh+var_50], rdx
0x18000112b  mov     [rbp+1Fh+var_44], r9d
0x18000112f  mov     [rbp+1Fh+var_58], 8
0x180001137  mov     rdx, [rax]
0x18000113a  test    rdx, rdx
0x18000113d  jz      short loc_180001153
0x18000113f  inc     rcx
0x180001142  cmp     [rdx+rcx*2], r9w
0x180001147  jnz     short loc_18000113F
0x180001149  lea     r8d, ds:2[rcx*2]
0x180001151  jmp     short loc_18000115A
0x180001153  lea     rdx, qword_180020CC0
0x18000115a  mov     rax, [rbp+1Fh+arg_20]
0x18000115e  mov     rcx, r10
0x180001161  mov     [rbp+1Fh+var_68], r8d
0x180001165  mov     [rbp+1Fh+var_70], rdx
0x180001169  mov     rdx, r11
0x18000116c  mov     [rbp+1Fh+var_64], r9d
0x180001170  mov     r8, [rax]
0x180001173  lea     rax, [rsp+0D0h+var_A0]
0x180001178  mov     [rbp+1Fh+var_80], r8
0x18000117c  xor     r8d, r8d
0x18000117f  mov     [rsp+0D0h+var_A8], rax
0x180001184  mov     [rsp+0D0h+var_B0], 9
0x18000118c  mov     [rbp+1Fh+var_78], 10h
0x180001194  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180001199  mov     rcx, [rbp+1Fh+var_10]
0x18000119d  xor     rcx, rsp; StackCookie
0x1800011a0  call    __security_check_cookie
0x1800011a5  add     rsp, 0D0h
0x1800011ac  pop     rbp
0x1800011ad  retn
```
