# PixEventDecoder::ReadEventWithNoFormatParameters(unsigned __int64,unsigned __int64 const *,unsigned __int64 const *,ushort *,uint)

- ea: `0x1800a3c44`
- end: `0x1800a3e2a`
- name: `?ReadEventWithNoFormatParameters@PixEventDecoder@@YA?AUEventData@1@_KPEB_K1PEAGI@Z`
- size: `486`
- prototype: `struct PixEventDecoder::EventData __high(unsigned __int64, const unsigned __int64 *, const unsigned __int64 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180023308`

## callees

- `0x180014368`
- `0x180064bac`
- `0x1800651a8`
- `0x1800a3c44`
- `0x1800bb92c`
- `0x1800bd8d0`
- `0x1800bd938`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__mbstowcs_s_l` at `0x1800a3dd6`
- `api-ms-win-crt-private-l1-1-0!_o__mbstowcs_s_l` at `0x1800a3dd6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800a3e05`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800a3e05`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x1800a3d8a`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x1800a3d8a`

## pseudocode

```c
__int64 __fastcall PixEventDecoder::ReadEventWithNoFormatParameters(
        __int64 a1,
        unsigned __int64 a2,
        char *a3,
        unsigned __int64 a4,
        unsigned __int16 *a5,
        unsigned __int8 a6)
{
  char *v8; // rdi
  unsigned __int8 v9; // dl
  char v10; // cl
  unsigned __int64 v11; // rax
  unsigned __int8 *v12; // r9
  unsigned __int64 v13; // rax
  _QWORD *String; // rax
  __int64 v15; // r15
  int v16; // esi
  __int64 v17; // r14
  int v18; // edi
  unsigned __int64 v20; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v21[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v22; // [rsp+90h] [rbp+40h] BYREF
  int v23; // [rsp+A0h] [rbp+50h] BYREF
  char v24; // [rsp+A8h] [rbp+58h] BYREF

  *(_QWORD *)a1 = 0;
  v8 = a3;
  *(_DWORD *)(a1 + 8) = 1024;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 40) = 0;
  if ( (unsigned __int64)a3 >= a4 )
    return a1;
  v23 = 1024;
  LOBYTE(v22) = 0;
  a6 = 0;
  PIXDecodeEventInfo(a2, &v20, (enum PixOp *)&v23, (unsigned __int8 *)&v22, &a6, (enum PixOp *)&v24);
  v9 = a6;
  v10 = v22;
  if ( (a6 & 0xF0) == 0xF0 )
  {
    v11 = *(_QWORD *)v8;
    v8 += 8;
    *(_DWORD *)(a1 + 40) += 8;
  }
  else
  {
    if ( !(_BYTE)v22 )
    {
LABEL_8:
      v12 = 0;
      goto LABEL_9;
    }
    v11 = (unsigned __int64)a6 >> 4;
  }
  *(_QWORD *)(a1 + 16) = v11;
  if ( !v10 )
    goto LABEL_8;
  v12 = &a6;
LABEL_9:
  if ( (v9 & 1) != 0 )
  {
    v13 = *(_QWORD *)v8;
    v8 += 8;
    *(_DWORD *)(a1 + 40) += 8;
    *(_QWORD *)(a1 + 24) = v13;
  }
  String = PixEventDecoder::ReadString(v21, v8, a4, v12);
  v15 = *(unsigned int *)String;
  v16 = *((_DWORD *)String + 1);
  v17 = String[2];
  v18 = *(_DWORD *)String;
  if ( (unsigned int)v15 > 0x4000 )
    v18 = 0x4000;
  if ( *((_BYTE *)String + 8) )
  {
    if ( dword_18033B7A0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 8LL) )
    {
      Init_thread_header(&dword_18033B7A0);
      if ( dword_18033B7A0 == -1 )
      {
        qword_18033B7A8 = _create_locale(0, ".UTF8");
        atexit(PixEventDecoder::ReadEventWithNoFormatParameters_::_19_::_dynamic_atexit_destructor_for__utf8Locale__);
        Init_thread_footer(&dword_18033B7A0);
      }
    }
    v22 = 0;
    if ( (unsigned int)_o__mbstowcs_s_l(&v22, a5, 0x4000, v17, v15, qword_18033B7A8) )
    {
      StringCchPrintfW(a5, 0x4000u, off_180324BA8);
      v18 = dword_180324BB0;
    }
    goto LABEL_20;
  }
  if ( !(unsigned int)_o_wcscpy_s(a5, 0x4000, String[2]) )
  {
LABEL_20:
    *(_DWORD *)(a1 + 40) += v16;
    *(_DWORD *)(a1 + 32) = v18;
    *(_DWORD *)(a1 + 36) = v16;
  }
  return a1;
}

```

## disassembly

```asm
0x1800a3c44  push    rbp
0x1800a3c46  push    rbx
0x1800a3c47  push    rsi
0x1800a3c48  push    rdi
0x1800a3c49  push    r13
0x1800a3c4b  push    r14
0x1800a3c4d  push    r15
0x1800a3c4f  mov     rbp, rsp
0x1800a3c52  sub     rsp, 50h
0x1800a3c56  mov     qword ptr [rcx], 0
0x1800a3c5d  mov     rbx, rcx
0x1800a3c60  mov     ecx, 400h
0x1800a3c65  mov     rsi, r9
0x1800a3c68  mov     rdi, r8
0x1800a3c6b  mov     rax, rdx
0x1800a3c6e  mov     [rbx+8], ecx
0x1800a3c71  mov     qword ptr [rbx+10h], 0
0x1800a3c79  mov     qword ptr [rbx+18h], 0
0x1800a3c81  mov     qword ptr [rbx+20h], 0
0x1800a3c89  mov     dword ptr [rbx+28h], 0
0x1800a3c90  cmp     r8, r9
0x1800a3c93  jnb     loc_1800A3E18
0x1800a3c99  mov     [rbp+arg_10], ecx
0x1800a3c9c  lea     r9, [rbp+arg_0]; unsigned __int8 *
0x1800a3ca0  lea     rcx, [rbp+arg_18]
0x1800a3ca4  mov     byte ptr [rbp+arg_0], 0
0x1800a3ca8  mov     [rsp+50h+var_28], rcx; enum PixOp *
0x1800a3cad  lea     r8, [rbp+arg_10]; enum PixOp *
0x1800a3cb1  lea     rcx, [rbp+arg_28]
0x1800a3cb5  mov     [rbp+arg_28], 0
0x1800a3cb9  mov     [rsp+50h+var_30], rcx; unsigned __int8 *
0x1800a3cbe  lea     rdx, [rbp+var_20]; unsigned __int64 *
0x1800a3cc2  mov     rcx, rax; unsigned __int64
0x1800a3cc5  call    ?PIXDecodeEventInfo@@YAX_KPEA_KPEAW4PixOp@@PEAE32@Z; PIXDecodeEventInfo(unsigned __int64,unsigned __int64 *,PixOp *,uchar *,uchar *,PixOp *)
0x1800a3cca  movzx   edx, [rbp+arg_28]
0x1800a3cce  mov     cl, byte ptr [rbp+arg_0]
0x1800a3cd1  mov     al, dl
0x1800a3cd3  and     al, 0F0h
0x1800a3cd5  cmp     al, 0F0h
0x1800a3cd7  jnz     short loc_1800A3CE6
0x1800a3cd9  mov     rax, [rdi]
0x1800a3cdc  add     rdi, 8
0x1800a3ce0  add     dword ptr [rbx+28h], 8
0x1800a3ce4  jmp     short loc_1800A3CF1
0x1800a3ce6  test    cl, cl
0x1800a3ce8  jz      short loc_1800A3CFF
0x1800a3cea  mov     rax, rdx
0x1800a3ced  shr     rax, 4
0x1800a3cf1  mov     [rbx+10h], rax
0x1800a3cf5  test    cl, cl
0x1800a3cf7  jz      short loc_1800A3CFF
0x1800a3cf9  lea     r9, [rbp+arg_28]
0x1800a3cfd  jmp     short loc_1800A3D02
0x1800a3cff  xor     r9d, r9d
0x1800a3d02  test    dl, 1
0x1800a3d05  jz      short loc_1800A3D16
0x1800a3d07  mov     rax, [rdi]
0x1800a3d0a  add     rdi, 8
0x1800a3d0e  add     dword ptr [rbx+28h], 8
0x1800a3d12  mov     [rbx+18h], rax
0x1800a3d16  mov     r8, rsi
0x1800a3d19  lea     rcx, [rbp+var_18]
0x1800a3d1d  mov     rdx, rdi
0x1800a3d20  call    ?ReadString@PixEventDecoder@@YA?AUSavedStringInfo@1@PEB_K0PEBE@Z; PixEventDecoder::ReadString(unsigned __int64 const *,unsigned __int64 const *,uchar const *)
0x1800a3d25  mov     r13d, 4000h
0x1800a3d2b  mov     r15d, [rax]
0x1800a3d2e  mov     esi, [rax+4]
0x1800a3d31  cmp     r15d, r13d
0x1800a3d34  mov     r14, [rax+10h]
0x1800a3d38  mov     edi, r15d
0x1800a3d3b  cmova   edi, r13d
0x1800a3d3f  cmp     byte ptr [rax+8], 0
0x1800a3d43  jz      loc_1800A3DFB
0x1800a3d49  mov     ecx, cs:_tls_index
0x1800a3d4f  mov     rax, gs:58h
0x1800a3d58  mov     edx, 8
0x1800a3d5d  mov     rax, [rax+rcx*8]
0x1800a3d61  mov     eax, [rdx+rax]
0x1800a3d64  cmp     cs:dword_18033B7A0, eax
0x1800a3d6a  jle     short loc_1800A3DAF
0x1800a3d6c  lea     rcx, dword_18033B7A0
0x1800a3d73  call    _Init_thread_header
0x1800a3d78  cmp     cs:dword_18033B7A0, 0FFFFFFFFh
0x1800a3d7f  jnz     short loc_1800A3DAF
0x1800a3d81  lea     rdx, Locale; ".UTF8"
0x1800a3d88  xor     ecx, ecx; Category
0x1800a3d8a  call    cs:__imp__create_locale
0x1800a3d90  lea     rcx, _PixEventDecoder__ReadEventWithNoFormatParameters____19____dynamic_atexit_destructor_for__utf8Locale__; void (__cdecl *)()
0x1800a3d97  mov     cs:qword_18033B7A8, rax
0x1800a3d9e  call    atexit
0x1800a3da3  lea     rcx, dword_18033B7A0
0x1800a3daa  call    _Init_thread_footer
0x1800a3daf  mov     rax, cs:qword_18033B7A8
0x1800a3db6  lea     rcx, [rbp+arg_0]
0x1800a3dba  mov     rdx, [rbp+arg_20]
0x1800a3dbe  mov     r9, r14
0x1800a3dc1  mov     [rsp+50h+var_28], rax
0x1800a3dc6  mov     r8, r13
0x1800a3dc9  mov     [rsp+50h+var_30], r15
0x1800a3dce  mov     [rbp+arg_0], 0
0x1800a3dd6  call    cs:__imp__o__mbstowcs_s_l
0x1800a3ddc  test    eax, eax
0x1800a3dde  jz      short loc_1800A3E0F
0x1800a3de0  mov     r8, cs:off_180324BA8; unsigned __int16 *
0x1800a3de7  mov     rdx, r13; unsigned __int64
0x1800a3dea  mov     rcx, [rbp+arg_20]; unsigned __int16 *
0x1800a3dee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a3df3  mov     edi, cs:dword_180324BB0
0x1800a3df9  jmp     short loc_1800A3E0F
0x1800a3dfb  mov     rcx, [rbp+arg_20]
0x1800a3dff  mov     r8, r14
0x1800a3e02  mov     rdx, r13
0x1800a3e05  call    cs:__imp__o_wcscpy_s
0x1800a3e0b  test    eax, eax
0x1800a3e0d  jnz     short loc_1800A3E18
0x1800a3e0f  add     [rbx+28h], esi
0x1800a3e12  mov     [rbx+20h], edi
0x1800a3e15  mov     [rbx+24h], esi
0x1800a3e18  mov     rax, rbx
0x1800a3e1b  add     rsp, 50h
0x1800a3e1f  pop     r15
0x1800a3e21  pop     r14
0x1800a3e23  pop     r13
0x1800a3e25  pop     rdi
0x1800a3e26  pop     rsi
0x1800a3e27  pop     rbx
0x1800a3e28  pop     rbp
0x1800a3e29  retn
```
