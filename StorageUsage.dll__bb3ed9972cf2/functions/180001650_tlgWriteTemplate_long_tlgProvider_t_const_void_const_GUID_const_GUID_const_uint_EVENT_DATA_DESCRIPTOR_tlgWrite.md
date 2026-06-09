# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001650`
- end: `0x1800018b3`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapperByVal@$07@@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapperByVal@$07@@5555555555545@Z`
- size: `611`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **, int **, int **, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a93c`

## callees

- `0x180001010`
- `0x180001650`
- `0x1800050f0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        int **a6,
        int **a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22,
        __int64 a23,
        __int64 a24)
{
  __int64 v25; // rcx
  int v26; // r8d
  int *v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  int *v30; // rdx
  __int64 v31; // rax
  int v32; // eax
  int *v33; // rdx
  _BYTE v35[32]; // [rsp+30h] [rbp-D0h] BYREF
  int *v36; // [rsp+50h] [rbp-B0h]
  int v37; // [rsp+58h] [rbp-A8h]
  int v38; // [rsp+5Ch] [rbp-A4h]
  int *v39; // [rsp+60h] [rbp-A0h]
  int v40; // [rsp+68h] [rbp-98h]
  int v41; // [rsp+6Ch] [rbp-94h]
  int *v42; // [rsp+70h] [rbp-90h]
  int v43; // [rsp+78h] [rbp-88h]
  int v44; // [rsp+7Ch] [rbp-84h]
  __int64 v45; // [rsp+80h] [rbp-80h]
  __int64 v46; // [rsp+88h] [rbp-78h]
  __int64 v47; // [rsp+90h] [rbp-70h]
  __int64 v48; // [rsp+98h] [rbp-68h]
  __int64 v49; // [rsp+A0h] [rbp-60h]
  __int64 v50; // [rsp+A8h] [rbp-58h]
  __int64 v51; // [rsp+B0h] [rbp-50h]
  __int64 v52; // [rsp+B8h] [rbp-48h]
  __int64 v53; // [rsp+C0h] [rbp-40h]
  __int64 v54; // [rsp+C8h] [rbp-38h]
  __int64 v55; // [rsp+D0h] [rbp-30h]
  __int64 v56; // [rsp+D8h] [rbp-28h]
  __int64 v57; // [rsp+E0h] [rbp-20h]
  __int64 v58; // [rsp+E8h] [rbp-18h]
  __int64 v59; // [rsp+F0h] [rbp-10h]
  __int64 v60; // [rsp+F8h] [rbp-8h]
  __int64 v61; // [rsp+100h] [rbp+0h]
  __int64 v62; // [rsp+108h] [rbp+8h]
  __int64 v63; // [rsp+110h] [rbp+10h]
  __int64 v64; // [rsp+118h] [rbp+18h]
  __int64 v65; // [rsp+120h] [rbp+20h]
  __int64 v66; // [rsp+128h] [rbp+28h]
  __int64 v67; // [rsp+130h] [rbp+30h]
  __int64 v68; // [rsp+138h] [rbp+38h]
  __int64 v69; // [rsp+140h] [rbp+40h]
  __int64 v70; // [rsp+148h] [rbp+48h]
  __int64 v71; // [rsp+150h] [rbp+50h]
  __int64 v72; // [rsp+158h] [rbp+58h]
  __int64 v73; // [rsp+160h] [rbp+60h]
  __int64 v74; // [rsp+168h] [rbp+68h]
  __int64 v75; // [rsp+170h] [rbp+70h]
  __int64 v76; // [rsp+178h] [rbp+78h]
  __int64 v77; // [rsp+180h] [rbp+80h]
  __int64 v78; // [rsp+188h] [rbp+88h]

  v77 = a24;
  v75 = a23;
  v25 = -1;
  v73 = a22;
  v26 = 2;
  v71 = a21;
  v69 = a20;
  v67 = a19;
  v65 = a18;
  v63 = a17;
  v61 = a16;
  v59 = a15;
  v57 = a14;
  v55 = a13;
  v53 = a12;
  v51 = a11;
  v49 = a10;
  v47 = a9;
  v45 = a8;
  v78 = 8;
  v76 = 4;
  v74 = 8;
  v27 = *a7;
  v72 = 8;
  v70 = 8;
  v68 = 8;
  v66 = 8;
  v64 = 8;
  v62 = 8;
  v60 = 8;
  v58 = 8;
  v56 = 8;
  v54 = 8;
  v52 = 8;
  v50 = 4;
  v48 = 4;
  v46 = 4;
  if ( v27 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_WORD *)v27 + v28) );
    v29 = 2 * v28 + 2;
  }
  else
  {
    v27 = &dword_180031EE4;
    v29 = 2;
  }
  v43 = v29;
  v42 = v27;
  v44 = 0;
  v30 = *a6;
  if ( *a6 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *((_WORD *)v30 + v31) );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &dword_180031EE4;
    v32 = 2;
  }
  v40 = v32;
  v39 = v30;
  v41 = 0;
  v33 = *a5;
  if ( *a5 )
  {
    do
      ++v25;
    while ( *((_WORD *)v33 + v25) );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v33 = &dword_180031EE4;
  }
  v36 = v33;
  v37 = v26;
  v38 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180040010, a2, 0, 0, 22, v35);
}

```

## disassembly

```asm
0x180001650  push    rbp
0x180001652  lea     rbp, [rsp-0A0h]
0x18000165a  sub     rsp, 1A0h
0x180001661  mov     rax, cs:__security_cookie
0x180001668  xor     rax, rsp
0x18000166b  mov     [rbp+0A0h+var_10], rax
0x180001672  mov     rax, [rbp+0A0h+arg_B8]
0x180001679  lea     r11, dword_180031EE4
0x180001680  mov     [rbp+0A0h+var_20], rax
0x180001687  xor     r9d, r9d
0x18000168a  mov     rax, [rbp+0A0h+arg_B0]
0x180001691  mov     r10, rdx
0x180001694  mov     [rbp+0A0h+var_30], rax
0x180001698  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000169c  mov     rax, [rbp+0A0h+arg_A8]
0x1800016a3  mov     [rbp+0A0h+var_40], rax
0x1800016a7  lea     r8d, [r9+2]
0x1800016ab  mov     rax, [rbp+0A0h+arg_A0]
0x1800016b2  mov     [rbp+0A0h+var_50], rax
0x1800016b6  mov     rax, [rbp+0A0h+arg_98]
0x1800016bd  mov     [rbp+0A0h+var_60], rax
0x1800016c1  mov     rax, [rbp+0A0h+arg_90]
0x1800016c8  mov     [rbp+0A0h+var_70], rax
0x1800016cc  mov     rax, [rbp+0A0h+arg_88]
0x1800016d3  mov     [rbp+0A0h+var_80], rax
0x1800016d7  mov     rax, [rbp+0A0h+arg_80]
0x1800016de  mov     [rbp+0A0h+var_90], rax
0x1800016e2  mov     rax, [rbp+0A0h+arg_78]
0x1800016e9  mov     [rbp+0A0h+var_A0], rax
0x1800016ed  mov     rax, [rbp+0A0h+arg_70]
0x1800016f4  mov     [rbp+0A0h+var_B0], rax
0x1800016f8  mov     rax, [rbp+0A0h+arg_68]
0x1800016ff  mov     [rbp+0A0h+var_C0], rax
0x180001703  mov     rax, [rbp+0A0h+arg_60]
0x18000170a  mov     [rbp+0A0h+var_D0], rax
0x18000170e  mov     rax, [rbp+0A0h+arg_58]
0x180001715  mov     [rbp+0A0h+var_E0], rax
0x180001719  mov     rax, [rbp+0A0h+arg_50]
0x180001720  mov     [rbp+0A0h+var_F0], rax
0x180001724  mov     rax, [rbp+0A0h+arg_48]
0x18000172b  mov     [rbp+0A0h+var_100], rax
0x18000172f  mov     rax, [rbp+0A0h+arg_40]
0x180001736  mov     [rbp+0A0h+var_110], rax
0x18000173a  mov     rax, [rbp+0A0h+arg_38]
0x180001741  mov     [rbp+0A0h+var_120], rax
0x180001745  mov     rax, [rbp+0A0h+arg_30]
0x18000174c  mov     [rbp+0A0h+var_18], 8
0x180001757  mov     [rbp+0A0h+var_28], 4
0x18000175f  mov     [rbp+0A0h+var_38], 8
0x180001767  mov     rdx, [rax]
0x18000176a  mov     [rbp+0A0h+var_48], 8
0x180001772  mov     [rbp+0A0h+var_58], 8
0x18000177a  mov     [rbp+0A0h+var_68], 8
0x180001782  mov     [rbp+0A0h+var_78], 8
0x18000178a  mov     [rbp+0A0h+var_88], 8
0x180001792  mov     [rbp+0A0h+var_98], 8
0x18000179a  mov     [rbp+0A0h+var_A8], 8
0x1800017a2  mov     [rbp+0A0h+var_B8], 8
0x1800017aa  mov     [rbp+0A0h+var_C8], 8
0x1800017b2  mov     [rbp+0A0h+var_D8], 8
0x1800017ba  mov     [rbp+0A0h+var_E8], 8
0x1800017c2  mov     [rbp+0A0h+var_F8], 4
0x1800017ca  mov     [rbp+0A0h+var_108], 4
0x1800017d2  mov     [rbp+0A0h+var_118], 4
0x1800017da  test    rdx, rdx
0x1800017dd  jz      short loc_1800017F5
0x1800017df  mov     rax, rcx
0x1800017e2  inc     rax
0x1800017e5  cmp     [rdx+rax*2], r9w
0x1800017ea  jnz     short loc_1800017E2
0x1800017ec  lea     eax, ds:2[rax*2]
0x1800017f3  jmp     short loc_1800017FB
0x1800017f5  mov     rdx, r11
0x1800017f8  mov     eax, r8d
0x1800017fb  mov     [rsp+1A0h+var_128], eax
0x1800017ff  mov     rax, [rbp+0A0h+arg_28]
0x180001806  mov     [rsp+1A0h+var_130], rdx
0x18000180b  mov     [rsp+1A0h+var_124], r9d
0x180001810  mov     rdx, [rax]
0x180001813  test    rdx, rdx
0x180001816  jz      short loc_18000182E
0x180001818  mov     rax, rcx
0x18000181b  inc     rax
0x18000181e  cmp     [rdx+rax*2], r9w
0x180001823  jnz     short loc_18000181B
0x180001825  lea     eax, ds:2[rax*2]
0x18000182c  jmp     short loc_180001834
0x18000182e  mov     rdx, r11
0x180001831  mov     eax, r8d
0x180001834  mov     [rsp+1A0h+var_138], eax
0x180001838  mov     rax, [rbp+0A0h+arg_20]
0x18000183f  mov     [rsp+1A0h+var_140], rdx
0x180001844  mov     [rsp+1A0h+var_134], r9d
0x180001849  mov     rdx, [rax]
0x18000184c  test    rdx, rdx
0x18000184f  jz      short loc_180001865
0x180001851  inc     rcx
0x180001854  cmp     [rdx+rcx*2], r9w
0x180001859  jnz     short loc_180001851
0x18000185b  lea     r8d, ds:2[rcx*2]
0x180001863  jmp     short loc_180001868
0x180001865  mov     rdx, r11
0x180001868  lea     rax, [rsp+1A0h+var_170]
0x18000186d  mov     [rsp+1A0h+var_150], rdx
0x180001872  mov     [rsp+1A0h+var_148], r8d
0x180001877  lea     rcx, dword_180040010
0x18000187e  mov     [rsp+1A0h+var_178], rax
0x180001883  xor     r8d, r8d
0x180001886  mov     rdx, r10
0x180001889  mov     [rsp+1A0h+var_180], 16h
0x180001891  mov     [rsp+1A0h+var_144], r9d
0x180001896  call    _tlgWriteTransfer_EventWriteTransfer
0x18000189b  mov     rcx, [rbp+0A0h+var_10]
0x1800018a2  xor     rcx, rsp; StackCookie
0x1800018a5  call    __security_check_cookie
0x1800018aa  add     rsp, 1A0h
0x1800018b1  pop     rbp
0x1800018b2  retn
```
