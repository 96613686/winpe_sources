# sub_1800BFE5C

- ea: `0x1800bfe5c`
- end: `0x1800c0315`
- name: `sub_1800BFE5C`
- size: `1209`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: ``

## callers

- `0x1800c0318`

## callees

- `0x18000d63c`
- `0x18000d8c8`
- `0x18000d8d0`
- `0x180019440`
- `0x180037600`
- `0x180037620`
- `0x180037640`
- `0x180037650`
- `0x180037654`
- `0x180037658`
- `0x18003767c`
- `0x18006e650`
- `0x180082818`
- `0x1800bf920`
- `0x1800bfbd8`
- `0x1800bfe5c`
- `0x1804c6020`
- `0x1804c6a50`
- `0x1804c714c`
- `0x1804c82c0`

## import_xrefs

- `mfc140u!??0CDC@@QEAA@XZ` at `0x1800bfff3`
- `mfc140u!??0CDC@@QEAA@XZ` at `0x1800bfff3`
- `mfc140u!__imp_??1CDC@@UEAA@XZ` at `0x1800c02e7`
- `mfc140u!__imp_??1CDC@@UEAA@XZ` at `0x1800c02e7`
- `mfc140u!??B?$CSimpleStringT@_W$00@ATL@@QEBAPEB_WXZ` at `0x1800c0278`
- `mfc140u!??B?$CSimpleStringT@_W$00@ATL@@QEBAPEB_WXZ` at `0x1800c0278`
- `mfc140u!?Attach@CDC@@QEAAHPEAUHDC__@@@Z` at `0x1800c002a`
- `mfc140u!?Attach@CDC@@QEAAHPEAUHDC__@@@Z` at `0x1800c002a`
- `mfc140u!?DeleteObject@CGdiObject@@QEAAHXZ` at `0x1800c02bd`
- `mfc140u!?DeleteObject@CGdiObject@@QEAAHXZ` at `0x1800c02bd`
- `mfc140u!?Detach@CDC@@QEAAPEAUHDC__@@XZ` at `0x1800c02dc`
- `mfc140u!?Detach@CDC@@QEAAPEAUHDC__@@XZ` at `0x1800c02dc`

## pseudocode

```c
void __fastcall sub_1800BFE5C(
        __int64 a1,
        int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned int *a7,
        _DWORD *a8,
        int a9,
        unsigned int a10,
        unsigned int a11,
        unsigned int a12,
        unsigned int a13)
{
  __int64 v15; // rax
  __int64 v16; // rdi
  unsigned __int64 v17; // rax
  __int64 v18; // rcx
  _QWORD *v19; // rax
  _QWORD *v20; // r14
  HDC v21; // rax
  __int64 v22; // rcx
  int v23; // edx
  int v24; // r8d
  __int64 v25; // rcx
  __int64 v26; // r8
  _QWORD *v27; // r14
  __int64 v28; // rcx
  CGdiObject *v29; // r14
  unsigned int v30; // edi
  __int64 v31; // rdx
  __int64 v32; // rdx
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // edx
  _DWORD *v36; // r9
  void (__fastcall *v37)(__int64, _QWORD, __int64, unsigned int *, CGdiObject *, unsigned int, __int64); // r12
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rcx
  unsigned int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // r8
  unsigned int v44; // [rsp+70h] [rbp-90h] BYREF
  int v45; // [rsp+74h] [rbp-8Ch] BYREF
  _QWORD *v46; // [rsp+78h] [rbp-88h] BYREF
  int v47; // [rsp+80h] [rbp-80h] BYREF
  _DWORD *v48; // [rsp+88h] [rbp-78h]
  double v49; // [rsp+90h] [rbp-70h] BYREF
  double v50; // [rsp+98h] [rbp-68h]
  __int64 v51; // [rsp+A0h] [rbp-60h]
  _BYTE v52[40]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v53[14]; // [rsp+D0h] [rbp-30h] BYREF

  v44 = a3;
  LODWORD(v46) = a2;
  v48 = a8;
  if ( a4 )
  {
    if ( a5 )
    {
      if ( a6 )
      {
        v15 = sub_1800BF920(a4);
        v16 = v15;
        if ( v15 )
        {
          v17 = sub_18000D63C(v15);
          if ( (unsigned int)v17 <= 0x23 )
          {
            v18 = 0x802006000LL;
            if ( _bittest64(&v18, v17) )
            {
              v45 = -1;
              v19 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
              v20 = v19;
              if ( v19 )
                sub_1804C6A50(*v19, 201488, 0);
              else
                v20 = 0;
              (*(void (__fastcall **)(_QWORD *, int *))(*v20 + 880LL))(v20, &v45);
              (*(void (__fastcall **)(_QWORD *, int *))(*v20 + 840LL))(v20, &v47);
              if ( (v45 & 1) == 0 && v47 >= 0 )
              {
                if ( *(_QWORD *)(a4 + 16) )
                {
                  CDC::CDC((CDC *)v52);
                  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a5 + 112LL))(a5) )
                  {
                    v21 = (HDC)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a5 + 112LL))(a5);
                    CDC::Attach((CDC *)v52, v21);
                    memset(v53, 0, 0x68u);
                    v53[6] = 0x3FC999999999999ALL;
                    v53[10] = 0x3FF0000000000000LL;
                    v53[7] = 0x3FF0000000000000LL;
                    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v16 + 272LL))(v16, v53);
                    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v16 + 752LL))(v16, &v53[9]);
                    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v16 + 888LL))(v16, &v53[1]);
                    v53[8] = sub_180037600(*(_QWORD *)(a4 + 16));
                    v53[6] = sub_180037620();
                    sub_18003767C(v22, &v49);
                    *(double *)&v53[3] = v49;
                    *(double *)&v53[4] = v50;
                    v53[5] = v51;
                    sub_18006E650(a6, v23, v24, (unsigned int)&v46, (__int64)&v44);
                    sub_180037640(*(_QWORD *)(a4 + 16), (unsigned int)v46);
                    sub_180037654(*(_QWORD *)(a4 + 16), v44);
                    if ( (unsigned int)sub_18000D63C(v16) == 25 )
                    {
                      (*(void (__fastcall **)(__int64, _QWORD **))(v26 + 384))(v25, &v46);
                      v27 = v46;
                      if ( v46 )
                        sub_1804C6A50(*v46, 197632, 0);
                      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v27 + 632LL))(v27, &v53[7]);
                    }
                    else
                    {
                      (*(void (__fastcall **)(__int64, _QWORD *))(v26 + 632))(v25, &v53[7]);
                    }
                    v49 = sub_18000D8C8(*(_QWORD *)(a4 + 16));
                    v50 = sub_18000D8D0(v28);
                    v51 = 0x3FF0000000000000LL;
                    v29 = (CGdiObject *)sub_180082818(v16, (unsigned int)v53, (unsigned int)v52, a6, (__int64)&v49);
                    if ( v29 )
                    {
                      v30 = a10;
                      v31 = a10;
                      if ( !a9 )
                        v31 = (unsigned int)*(__int16 *)(a4 + 2);
                      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)a1 + 16LL))(
                        a1,
                        v31,
                        a12,
                        a11,
                        a5);
                      v32 = a10;
                      if ( !a9 )
                        v32 = (unsigned int)*(__int16 *)(a4 + 2);
                      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, unsigned int, __int64))(*(_QWORD *)a1 + 24LL))(
                        a1,
                        v32,
                        a13,
                        a12,
                        a11,
                        a5);
                      if ( a7 && *v48 )
                      {
                        v33 = sub_180037650(*(_QWORD *)(a4 + 16));
                        *a7 = v33;
                        v34 = sub_180037658(*(_QWORD *)(a4 + 16), v33);
                        a7[1] = v34;
                        a7[2] = v35;
                        a7[3] = v34;
                        *v36 = 0;
                      }
                      v37 = *(void (__fastcall **)(__int64, _QWORD, __int64, unsigned int *, CGdiObject *, unsigned int, __int64))(*(_QWORD *)a5 + 104LL);
                      v38 = sub_180019440(*(_QWORD *)(a4 + 16));
                      v39 = ATL::CSimpleStringT<wchar_t,1>::operator wchar_t const *(v38);
                      if ( !a9 )
                        v30 = *(__int16 *)(a4 + 2);
                      sub_180037658(*(_QWORD *)(a4 + 16), v39);
                      v41 = sub_180037650(v40);
                      v37(a5, v41, v43, a7, v29, v30, v42);
                      CGdiObject::DeleteObject(v29);
                      (*(void (__fastcall **)(CGdiObject *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 1);
                    }
                    CDC::Detach((CDC *)v52);
                  }
                  CDC::~CDC((CDC *)v52);
                }
                else
                {
                  sub_1800BFBD8(a1, (_DWORD)v46, v44, a4, a5, a6, (__int64)a7, (__int64)v48, a9, a10, a11, a12, a13);
                }
              }
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800bfe5c  mov     rax, rsp
0x1800bfe5f  push    rbp
0x1800bfe60  push    rbx
0x1800bfe61  push    rsi
0x1800bfe62  push    rdi
0x1800bfe63  push    r12
0x1800bfe65  push    r13
0x1800bfe67  push    r14
0x1800bfe69  push    r15
0x1800bfe6b  lea     rbp, [rsp-68h]
0x1800bfe70  sub     rsp, 168h
0x1800bfe77  movaps  xmmword ptr [rax-58h], xmm6
0x1800bfe7b  mov     rax, cs:__security_cookie
0x1800bfe82  xor     rax, rsp
0x1800bfe85  mov     [rbp+0A0h+var_60], rax
0x1800bfe89  mov     rbx, r9
0x1800bfe8c  mov     [rsp+1A0h+var_130], r8d
0x1800bfe91  mov     dword ptr [rsp+1A0h+var_128], edx
0x1800bfe95  mov     r12, rcx
0x1800bfe98  mov     rsi, [rbp+0A0h+arg_20]
0x1800bfe9f  mov     r13, [rbp+0A0h+arg_28]
0x1800bfea6  mov     r15, [rbp+0A0h+arg_30]
0x1800bfead  mov     rax, [rbp+0A0h+arg_38]
0x1800bfeb4  mov     [rbp+0A0h+var_118], rax
0x1800bfeb8  test    r9, r9
0x1800bfebb  jz      loc_1800C02ED
0x1800bfec1  test    rsi, rsi
0x1800bfec4  jz      loc_1800C02ED
0x1800bfeca  test    r13, r13
0x1800bfecd  jz      loc_1800C02ED
0x1800bfed3  mov     rcx, rbx
0x1800bfed6  call    sub_1800BF920
0x1800bfedb  mov     rdi, rax
0x1800bfede  test    rax, rax
0x1800bfee1  jz      loc_1800C02ED
0x1800bfee7  mov     rcx, rax
0x1800bfeea  call    sub_18000D63C
0x1800bfeef  cmp     eax, 23h ; '#'
0x1800bfef2  ja      loc_1800C02ED
0x1800bfef8  mov     rcx, 802006000h
0x1800bff02  bt      rcx, rax
0x1800bff06  jnb     loc_1800C02ED
0x1800bff0c  mov     [rsp+1A0h+var_12C], 0FFFFFFFFh
0x1800bff14  mov     rax, [rdi]
0x1800bff17  mov     rcx, rdi
0x1800bff1a  mov     rax, [rax+10h]
0x1800bff1e  call    cs:__guard_dispatch_icall_fptr
0x1800bff24  mov     r14, rax
0x1800bff27  test    rax, rax
0x1800bff2a  jz      short loc_1800BFF3E
0x1800bff2c  xor     r8d, r8d
0x1800bff2f  mov     edx, 31310h
0x1800bff34  mov     rcx, [rax]
0x1800bff37  call    sub_1804C6A50
0x1800bff3c  jmp     short loc_1800BFF41
0x1800bff3e  xor     r14d, r14d
0x1800bff41  mov     rax, [r14]
0x1800bff44  lea     rdx, [rsp+1A0h+var_12C]
0x1800bff49  mov     rcx, r14
0x1800bff4c  mov     rax, [rax+370h]
0x1800bff53  call    cs:__guard_dispatch_icall_fptr
0x1800bff59  mov     rax, [r14]
0x1800bff5c  lea     rdx, [rbp+0A0h+var_120]
0x1800bff60  mov     rcx, r14
0x1800bff63  mov     rax, [rax+348h]
0x1800bff6a  call    cs:__guard_dispatch_icall_fptr
0x1800bff70  test    byte ptr [rsp+1A0h+var_12C], 1
0x1800bff75  jnz     loc_1800C02ED
0x1800bff7b  cmp     [rbp+0A0h+var_120], 0
0x1800bff7f  jl      loc_1800C02ED
0x1800bff85  cmp     qword ptr [rbx+10h], 0
0x1800bff8a  jnz     short loc_1800BFFEF
0x1800bff8c  mov     eax, [rbp+0A0h+arg_60]
0x1800bff92  mov     [rsp+1A0h+var_140], eax
0x1800bff96  mov     eax, [rbp+0A0h+arg_58]
0x1800bff9c  mov     [rsp+1A0h+var_148], eax
0x1800bffa0  mov     eax, [rbp+0A0h+arg_50]
0x1800bffa6  mov     [rsp+1A0h+var_150], eax
0x1800bffaa  mov     eax, [rbp+0A0h+arg_48]
0x1800bffb0  mov     [rsp+1A0h+var_158], eax
0x1800bffb4  mov     eax, [rbp+0A0h+arg_40]
0x1800bffba  mov     [rsp+1A0h+var_160], eax
0x1800bffbe  mov     r9, [rbp+0A0h+var_118]
0x1800bffc2  mov     [rsp+1A0h+var_168], r9
0x1800bffc7  mov     [rsp+1A0h+var_170], r15
0x1800bffcc  mov     [rsp+1A0h+var_178], r13
0x1800bffd1  mov     [rsp+1A0h+var_180], rsi
0x1800bffd6  mov     r9, rbx
0x1800bffd9  mov     r8d, [rsp+1A0h+var_130]
0x1800bffde  mov     edx, dword ptr [rsp+1A0h+var_128]
0x1800bffe2  mov     rcx, r12
0x1800bffe5  call    sub_1800BFBD8
0x1800bffea  jmp     loc_1800C02ED
0x1800bffef  lea     rcx, [rbp+0A0h+var_F8]
0x1800bfff3  call    cs:??0CDC@@QEAA@XZ; CDC::CDC(void)
0x1800bfff9  nop
0x1800bfffa  mov     rax, [rsi]
0x1800bfffd  mov     rcx, rsi
0x1800c0000  mov     rax, [rax+70h]
0x1800c0004  call    cs:__guard_dispatch_icall_fptr
0x1800c000a  test    rax, rax
0x1800c000d  jz      loc_1800C02E3
0x1800c0013  mov     rax, [rsi]
0x1800c0016  mov     rcx, rsi
0x1800c0019  mov     rax, [rax+70h]
0x1800c001d  call    cs:__guard_dispatch_icall_fptr
0x1800c0023  mov     rdx, rax
0x1800c0026  lea     rcx, [rbp+0A0h+var_F8]
0x1800c002a  call    cs:?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1800c0030  xor     edx, edx; Val
0x1800c0032  lea     r8d, [rdx+68h]; Size
0x1800c0036  lea     rcx, [rbp+0A0h+var_D0]; void *
0x1800c003a  call    memset
0x1800c003f  movsd   xmm0, cs:qword_1805D2508
0x1800c0047  movsd   [rbp+0A0h+var_A0], xmm0
0x1800c004c  movsd   xmm6, cs:pExceptionObject
0x1800c0054  movsd   [rbp+0A0h+var_80], xmm6
0x1800c0059  movsd   [rbp+0A0h+var_98], xmm6
0x1800c005e  mov     rax, [rdi]
0x1800c0061  lea     rdx, [rbp+0A0h+var_D0]
0x1800c0065  mov     rcx, rdi
0x1800c0068  mov     rax, [rax+110h]
0x1800c006f  call    cs:__guard_dispatch_icall_fptr
0x1800c0075  mov     rax, [rdi]
0x1800c0078  lea     rdx, [rbp+0A0h+var_88]
0x1800c007c  mov     rcx, rdi
0x1800c007f  mov     rax, [rax+2F0h]
0x1800c0086  call    cs:__guard_dispatch_icall_fptr
0x1800c008c  mov     rax, [rdi]
0x1800c008f  lea     rdx, [rbp+0A0h+var_C8]
0x1800c0093  mov     rcx, rdi
0x1800c0096  mov     rax, [rax+378h]
0x1800c009d  call    cs:__guard_dispatch_icall_fptr
0x1800c00a3  mov     rcx, [rbx+10h]
0x1800c00a7  call    sub_180037600
0x1800c00ac  movsd   [rbp+0A0h+var_90], xmm0
0x1800c00b1  call    sub_180037620
0x1800c00b6  movsd   [rbp+0A0h+var_A0], xmm0
0x1800c00bb  lea     rdx, [rbp+0A0h+var_110]
0x1800c00bf  call    sub_18003767C
0x1800c00c4  movsd   xmm1, [rbp+0A0h+var_110]
0x1800c00c9  movsd   [rbp+0A0h+var_B8], xmm1
0x1800c00ce  movsd   xmm2, [rbp+0A0h+var_108]
0x1800c00d3  movsd   [rbp+0A0h+var_B0], xmm2
0x1800c00d8  movsd   xmm0, [rbp+0A0h+var_100]
0x1800c00dd  movsd   [rbp+0A0h+var_A8], xmm0
0x1800c00e2  lea     rax, [rsp+1A0h+var_130]
0x1800c00e7  mov     [rsp+1A0h+var_180], rax
0x1800c00ec  lea     r9, [rsp+1A0h+var_128]
0x1800c00f1  mov     rcx, r13
0x1800c00f4  call    sub_18006E650
0x1800c00f9  mov     edx, dword ptr [rsp+1A0h+var_128]
0x1800c00fd  mov     rcx, [rbx+10h]
0x1800c0101  call    sub_180037640
0x1800c0106  mov     edx, [rsp+1A0h+var_130]
0x1800c010a  mov     rcx, [rbx+10h]
0x1800c010e  call    sub_180037654
0x1800c0113  mov     r8, [rdi]
0x1800c0116  mov     rcx, rdi
0x1800c0119  call    sub_18000D63C
0x1800c011e  cmp     eax, 19h
0x1800c0121  jnz     short loc_1800C015E
0x1800c0123  lea     rdx, [rsp+1A0h+var_128]
0x1800c0128  mov     rax, [r8+180h]
0x1800c012f  call    cs:__guard_dispatch_icall_fptr
0x1800c0135  mov     r14, [rsp+1A0h+var_128]
0x1800c013a  test    r14, r14
0x1800c013d  jz      short loc_1800C014F
0x1800c013f  xor     r8d, r8d
0x1800c0142  mov     edx, 30400h
0x1800c0147  mov     rcx, [r14]
0x1800c014a  call    sub_1804C6A50
0x1800c014f  mov     rax, [r14]
0x1800c0152  mov     rcx, r14
0x1800c0155  mov     rax, [rax+278h]
0x1800c015c  jmp     short loc_1800C0165
0x1800c015e  mov     rax, [r8+278h]
0x1800c0165  lea     rdx, [rbp+0A0h+var_98]
0x1800c0169  call    cs:__guard_dispatch_icall_fptr
0x1800c016f  mov     rcx, [rbx+10h]
0x1800c0173  call    sub_18000D8C8
0x1800c0178  movsd   [rbp+0A0h+var_110], xmm0
0x1800c017d  call    sub_18000D8D0
0x1800c0182  movsd   [rbp+0A0h+var_108], xmm0
0x1800c0187  movsd   [rbp+0A0h+var_100], xmm6
0x1800c018c  lea     rax, [rbp+0A0h+var_110]
0x1800c0190  mov     [rsp+1A0h+var_180], rax
0x1800c0195  mov     r9, r13
0x1800c0198  lea     r8, [rbp+0A0h+var_F8]
0x1800c019c  lea     rdx, [rbp+0A0h+var_D0]
0x1800c01a0  mov     rcx, rdi
0x1800c01a3  call    sub_180082818
0x1800c01a8  mov     r14, rax
0x1800c01ab  test    rax, rax
0x1800c01ae  jz      loc_1800C02D8
0x1800c01b4  mov     rax, [r12]
0x1800c01b8  mov     edi, [rbp+0A0h+arg_48]
0x1800c01be  mov     r13d, [rbp+0A0h+arg_40]
0x1800c01c5  test    r13d, r13d
0x1800c01c8  mov     edx, edi
0x1800c01ca  jnz     short loc_1800C01D0
0x1800c01cc  movsx   edx, word ptr [rbx+2]
0x1800c01d0  mov     [rsp+1A0h+var_180], rsi
0x1800c01d5  mov     r9d, [rbp+0A0h+arg_50]
0x1800c01dc  mov     r8d, [rbp+0A0h+arg_58]
0x1800c01e3  mov     rcx, r12
0x1800c01e6  mov     rax, [rax+10h]
0x1800c01ea  call    cs:__guard_dispatch_icall_fptr
0x1800c01f0  mov     rax, [r12]
0x1800c01f4  mov     r10, [rax+18h]
0x1800c01f8  test    r13d, r13d
0x1800c01fb  mov     edx, edi
0x1800c01fd  jnz     short loc_1800C0203
0x1800c01ff  movsx   edx, word ptr [rbx+2]
0x1800c0203  mov     [rsp+1A0h+var_178], rsi
0x1800c0208  mov     eax, [rbp+0A0h+arg_50]
0x1800c020e  mov     dword ptr [rsp+1A0h+var_180], eax
0x1800c0212  mov     r9d, [rbp+0A0h+arg_58]
0x1800c0219  mov     r8d, [rbp+0A0h+arg_60]
0x1800c0220  mov     rcx, r12
0x1800c0223  mov     rax, r10
0x1800c0226  call    cs:__guard_dispatch_icall_fptr
0x1800c022c  test    r15, r15
0x1800c022f  jz      short loc_1800C0265
0x1800c0231  mov     r9, [rbp+0A0h+var_118]
0x1800c0235  cmp     dword ptr [r9], 0
0x1800c0239  jz      short loc_1800C0265
0x1800c023b  mov     rcx, [rbx+10h]
0x1800c023f  call    sub_180037650
0x1800c0244  mov     edx, eax
0x1800c0246  mov     [r15], eax
0x1800c0249  mov     rcx, [rbx+10h]
0x1800c024d  call    sub_180037658
0x1800c0252  mov     [r15+4], eax
0x1800c0256  mov     [r15+8], edx
0x1800c025a  mov     [r15+0Ch], eax
0x1800c025e  mov     dword ptr [r9], 0
0x1800c0265  mov     rax, [rsi]
0x1800c0268  mov     r12, [rax+68h]
0x1800c026c  mov     rcx, [rbx+10h]
0x1800c0270  call    sub_180019440
0x1800c0275  mov     rcx, rax
0x1800c0278  call    cs:??B?$CSimpleStringT@_W$00@ATL@@QEBAPEB_WXZ; ATL::CSimpleStringT<wchar_t,1>::operator wchar_t const *(void)
0x1800c027e  mov     rdx, rax
0x1800c0281  test    r13d, r13d
0x1800c0284  jnz     short loc_1800C028A
0x1800c0286  movsx   edi, word ptr [rbx+2]
0x1800c028a  mov     rcx, [rbx+10h]
0x1800c028e  call    sub_180037658
0x1800c0293  mov     r8d, eax
0x1800c0296  call    sub_180037650
0x1800c029b  mov     [rsp+1A0h+var_170], rdx
0x1800c02a0  mov     dword ptr [rsp+1A0h+var_178], edi
0x1800c02a4  mov     [rsp+1A0h+var_180], r14
0x1800c02a9  mov     r9, r15
0x1800c02ac  mov     edx, eax
0x1800c02ae  mov     rcx, rsi
0x1800c02b1  mov     rax, r12
0x1800c02b4  call    cs:__guard_dispatch_icall_fptr
0x1800c02ba  mov     rcx, r14
0x1800c02bd  call    cs:?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1800c02c3  mov     rax, [r14]
0x1800c02c6  mov     edx, 1
0x1800c02cb  mov     rcx, r14
0x1800c02ce  mov     rax, [rax+8]
0x1800c02d2  call    cs:__guard_dispatch_icall_fptr
0x1800c02d8  lea     rcx, [rbp+0A0h+var_F8]
0x1800c02dc  call    cs:?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1800c02e2  nop
0x1800c02e3  lea     rcx, [rbp+0A0h+var_F8]
0x1800c02e7  call    cs:__imp_??1CDC@@UEAA@XZ; CDC::~CDC(void)
0x1800c02ed  mov     rcx, [rbp+0A0h+var_60]
0x1800c02f1  xor     rcx, rsp; StackCookie
0x1800c02f4  call    __security_check_cookie
0x1800c02f9  movaps  xmm6, [rsp+1A0h+var_50]
0x1800c0301  add     rsp, 168h
0x1800c0308  pop     r15
0x1800c030a  pop     r14
0x1800c030c  pop     r13
0x1800c030e  pop     r12
0x1800c0310  pop     rdi
0x1800c0311  pop     rsi
0x1800c0312  pop     rbx
0x1800c0313  pop     rbp
0x1800c0314  retn
```
