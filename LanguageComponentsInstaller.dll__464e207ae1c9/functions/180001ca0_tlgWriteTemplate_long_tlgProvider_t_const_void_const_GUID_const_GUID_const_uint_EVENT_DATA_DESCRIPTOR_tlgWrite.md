# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001ca0`
- end: `0x180001f90`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: `__int64 __fastcall(int, int, int, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, __int64 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64 **, __int64, const unsigned __int16 **, __int64 **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180018c50`
- `0x18001ae38`
- `0x180024e50`

## callees

- `0x180001ca0`
- `0x1800020dc`
- `0x180003520`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        int a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10,
        __int64 **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        __int64 **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        __int64 **a19,
        __int64 a20,
        __int64 a21,
        const unsigned __int16 **a22)
{
  __int64 v24; // rdx
  int v26; // r8d
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  int v30; // r9d
  __int64 *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  __int64 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  __int64 *v46; // rcx
  __int64 v47; // rax
  const unsigned __int16 *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  const unsigned __int16 *v51; // rcx
  struct _EVENT_DATA_DESCRIPTOR v53; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v54; // [rsp+50h] [rbp-B0h]
  __int64 v55; // [rsp+58h] [rbp-A8h]
  __int64 v56; // [rsp+60h] [rbp-A0h]
  __int64 v57; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v58; // [rsp+70h] [rbp-90h]
  int v59; // [rsp+78h] [rbp-88h]
  int v60; // [rsp+7Ch] [rbp-84h]
  __int64 v61; // [rsp+80h] [rbp-80h]
  __int64 v62; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v63; // [rsp+90h] [rbp-70h]
  int v64; // [rsp+98h] [rbp-68h]
  int v65; // [rsp+9Ch] [rbp-64h]
  __int64 v66; // [rsp+A0h] [rbp-60h]
  __int64 v67; // [rsp+A8h] [rbp-58h]
  __int64 *v68; // [rsp+B0h] [rbp-50h]
  int v69; // [rsp+B8h] [rbp-48h]
  int v70; // [rsp+BCh] [rbp-44h]
  __int64 v71; // [rsp+C0h] [rbp-40h]
  __int64 v72; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v73; // [rsp+D0h] [rbp-30h]
  int v74; // [rsp+D8h] [rbp-28h]
  int v75; // [rsp+DCh] [rbp-24h]
  __int64 v76; // [rsp+E0h] [rbp-20h]
  __int64 v77; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v78; // [rsp+F0h] [rbp-10h]
  int v79; // [rsp+F8h] [rbp-8h]
  int v80; // [rsp+FCh] [rbp-4h]
  __int64 *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  __int64 *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  __int64 v92; // [rsp+140h] [rbp+40h]
  __int64 v93; // [rsp+148h] [rbp+48h]
  __int64 v94; // [rsp+150h] [rbp+50h]
  __int64 v95; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v96; // [rsp+160h] [rbp+60h]
  int v97; // [rsp+168h] [rbp+68h]
  int v98; // [rsp+16Ch] [rbp+6Ch]

  v24 = -1;
  v26 = 1;
  v27 = *a22;
  if ( *a22 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_BYTE *)v27 + v28) );
    v29 = v28 + 1;
  }
  else
  {
    v27 = &dword_18002C87C;
    v29 = 1;
  }
  v97 = v29;
  v30 = 2;
  v94 = a21;
  v92 = a20;
  v96 = v27;
  v98 = 0;
  v95 = 4;
  v31 = *a19;
  v93 = 4;
  if ( v31 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &qword_18002D2C0;
    v33 = 2;
  }
  v90 = v33;
  v89 = v31;
  v91 = 0;
  v34 = *a18;
  if ( *a18 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &dword_18002C87C;
    v36 = 1;
  }
  v87 = v36;
  v84 = a17;
  v86 = v34;
  v88 = 0;
  v85 = 4;
  v37 = *a16;
  if ( *a16 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_WORD *)v37 + v38) );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &qword_18002D2C0;
    v39 = 2;
  }
  v82 = v39;
  v81 = v37;
  v83 = 0;
  v40 = *a15;
  if ( *a15 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_BYTE *)v40 + v41) );
    v42 = v41 + 1;
  }
  else
  {
    v40 = &dword_18002C87C;
    v42 = 1;
  }
  v79 = v42;
  v76 = a14;
  v78 = v40;
  v80 = 0;
  v77 = 4;
  v43 = *a13;
  if ( *a13 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &dword_18002C87C;
    v45 = 1;
  }
  v74 = v45;
  v71 = a12;
  v73 = v43;
  v75 = 0;
  v72 = 4;
  v46 = *a11;
  if ( *a11 )
  {
    v47 = -1;
    do
      ++v47;
    while ( *((_WORD *)v46 + v47) );
    v30 = 2 * v47 + 2;
  }
  else
  {
    v46 = &qword_18002D2C0;
  }
  v66 = a10;
  v68 = v46;
  v69 = v30;
  v70 = 0;
  v48 = *a9;
  v67 = 4;
  if ( v48 )
  {
    v49 = -1;
    do
      ++v49;
    while ( *((_BYTE *)v48 + v49) );
    v50 = v49 + 1;
  }
  else
  {
    v48 = &dword_18002C87C;
    v50 = 1;
  }
  v64 = v50;
  v61 = a8;
  v63 = v48;
  v65 = 0;
  v62 = 4;
  v51 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v51 + v24) );
    v26 = v24 + 1;
  }
  else
  {
    v51 = &dword_18002C87C;
  }
  v56 = a6;
  v54 = a5;
  v58 = v51;
  v59 = v26;
  v60 = 0;
  v57 = 4;
  v55 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x14u, &v53);
}

```

## disassembly

```asm
0x180001ca0  push    rbp
0x180001ca2  push    rbx
0x180001ca3  push    rsi
0x180001ca4  push    rdi
0x180001ca5  push    r15
0x180001ca7  lea     rbp, [rsp-80h]
0x180001cac  sub     rsp, 180h
0x180001cb3  mov     rax, cs:__security_cookie
0x180001cba  xor     rax, rsp
0x180001cbd  mov     [rbp+0A0h+var_30], rax
0x180001cc1  mov     rax, [rbp+0A0h+arg_A8]
0x180001cc8  lea     rsi, dword_18002C87C
0x180001ccf  mov     r11, rdx
0x180001cd2  mov     r10, rcx
0x180001cd5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001cd9  xor     edi, edi
0x180001cdb  mov     rbx, r8
0x180001cde  mov     r8d, 1
0x180001ce4  mov     rcx, [rax]
0x180001ce7  test    rcx, rcx
0x180001cea  jz      short loc_180001CFC
0x180001cec  mov     rax, rdx
0x180001cef  inc     rax
0x180001cf2  cmp     [rcx+rax], dil
0x180001cf6  jnz     short loc_180001CEF
0x180001cf8  inc     eax
0x180001cfa  jmp     short loc_180001D02
0x180001cfc  mov     rcx, rsi
0x180001cff  mov     eax, r8d
0x180001d02  mov     [rbp+0A0h+var_38], eax
0x180001d05  mov     r9d, 2
0x180001d0b  mov     rax, [rbp+0A0h+arg_A0]
0x180001d12  mov     [rbp+0A0h+var_50], rax
0x180001d16  mov     rax, [rbp+0A0h+arg_98]
0x180001d1d  mov     [rbp+0A0h+var_60], rax
0x180001d21  mov     rax, [rbp+0A0h+arg_90]
0x180001d28  mov     [rbp+0A0h+var_40], rcx
0x180001d2c  mov     [rbp+0A0h+var_34], edi
0x180001d2f  mov     [rbp+0A0h+var_48], 4
0x180001d37  mov     rcx, [rax]
0x180001d3a  mov     [rbp+0A0h+var_58], 4
0x180001d42  test    rcx, rcx
0x180001d45  jz      short loc_180001D5C
0x180001d47  mov     rax, rdx
0x180001d4a  inc     rax
0x180001d4d  cmp     [rcx+rax*2], di
0x180001d51  jnz     short loc_180001D4A
0x180001d53  lea     eax, ds:2[rax*2]
0x180001d5a  jmp     short loc_180001D66
0x180001d5c  lea     rcx, qword_18002D2C0
0x180001d63  mov     eax, r9d
0x180001d66  mov     [rbp+0A0h+var_68], eax
0x180001d69  mov     rax, [rbp+0A0h+arg_88]
0x180001d70  mov     [rbp+0A0h+var_70], rcx
0x180001d74  mov     [rbp+0A0h+var_64], edi
0x180001d77  mov     rcx, [rax]
0x180001d7a  test    rcx, rcx
0x180001d7d  jz      short loc_180001D8F
0x180001d7f  mov     rax, rdx
0x180001d82  inc     rax
0x180001d85  cmp     [rcx+rax], dil
0x180001d89  jnz     short loc_180001D82
0x180001d8b  inc     eax
0x180001d8d  jmp     short loc_180001D95
0x180001d8f  mov     rcx, rsi
0x180001d92  mov     eax, r8d
0x180001d95  mov     [rbp+0A0h+var_78], eax
0x180001d98  mov     rax, [rbp+0A0h+arg_80]
0x180001d9f  mov     [rbp+0A0h+var_90], rax
0x180001da3  mov     rax, [rbp+0A0h+arg_78]
0x180001daa  mov     [rbp+0A0h+var_80], rcx
0x180001dae  mov     [rbp+0A0h+var_74], edi
0x180001db1  mov     [rbp+0A0h+var_88], 4
0x180001db9  mov     rcx, [rax]
0x180001dbc  test    rcx, rcx
0x180001dbf  jz      short loc_180001DD6
0x180001dc1  mov     rax, rdx
0x180001dc4  inc     rax
0x180001dc7  cmp     [rcx+rax*2], di
0x180001dcb  jnz     short loc_180001DC4
0x180001dcd  lea     eax, ds:2[rax*2]
0x180001dd4  jmp     short loc_180001DE0
0x180001dd6  lea     rcx, qword_18002D2C0
0x180001ddd  mov     eax, r9d
0x180001de0  mov     [rbp+0A0h+var_98], eax
0x180001de3  mov     rax, [rbp+0A0h+arg_70]
0x180001dea  mov     [rbp+0A0h+var_A0], rcx
0x180001dee  mov     [rbp+0A0h+var_94], edi
0x180001df1  mov     rcx, [rax]
0x180001df4  test    rcx, rcx
0x180001df7  jz      short loc_180001E09
0x180001df9  mov     rax, rdx
0x180001dfc  inc     rax
0x180001dff  cmp     [rcx+rax], dil
0x180001e03  jnz     short loc_180001DFC
0x180001e05  inc     eax
0x180001e07  jmp     short loc_180001E0F
0x180001e09  mov     rcx, rsi
0x180001e0c  mov     eax, r8d
0x180001e0f  mov     [rbp+0A0h+var_A8], eax
0x180001e12  mov     rax, [rbp+0A0h+arg_68]
0x180001e19  mov     [rbp+0A0h+var_C0], rax
0x180001e1d  mov     rax, [rbp+0A0h+arg_60]
0x180001e24  mov     [rbp+0A0h+var_B0], rcx
0x180001e28  mov     [rbp+0A0h+var_A4], edi
0x180001e2b  mov     [rbp+0A0h+var_B8], 4
0x180001e33  mov     rcx, [rax]
0x180001e36  test    rcx, rcx
0x180001e39  jz      short loc_180001E4B
0x180001e3b  mov     rax, rdx
0x180001e3e  inc     rax
0x180001e41  cmp     [rcx+rax], dil
0x180001e45  jnz     short loc_180001E3E
0x180001e47  inc     eax
0x180001e49  jmp     short loc_180001E51
0x180001e4b  mov     rcx, rsi
0x180001e4e  mov     eax, r8d
0x180001e51  mov     [rbp+0A0h+var_C8], eax
0x180001e54  mov     rax, [rbp+0A0h+arg_58]
0x180001e5b  mov     [rbp+0A0h+var_E0], rax
0x180001e5f  mov     rax, [rbp+0A0h+arg_50]
0x180001e66  mov     [rbp+0A0h+var_D0], rcx
0x180001e6a  mov     [rbp+0A0h+var_C4], edi
0x180001e6d  mov     [rbp+0A0h+var_D8], 4
0x180001e75  mov     rcx, [rax]
0x180001e78  test    rcx, rcx
0x180001e7b  jz      short loc_180001E93
0x180001e7d  mov     rax, rdx
0x180001e80  inc     rax
0x180001e83  cmp     [rcx+rax*2], di
0x180001e87  jnz     short loc_180001E80
0x180001e89  lea     r9d, ds:2[rax*2]
0x180001e91  jmp     short loc_180001E9A
0x180001e93  lea     rcx, qword_18002D2C0
0x180001e9a  mov     rax, [rbp+0A0h+arg_48]
0x180001ea1  mov     [rbp+0A0h+var_100], rax
0x180001ea5  mov     rax, [rbp+0A0h+arg_40]
0x180001eac  mov     [rbp+0A0h+var_F0], rcx
0x180001eb0  mov     [rbp+0A0h+var_E8], r9d
0x180001eb4  mov     [rbp+0A0h+var_E4], edi
0x180001eb7  mov     rcx, [rax]
0x180001eba  mov     [rbp+0A0h+var_F8], 4
0x180001ec2  test    rcx, rcx
0x180001ec5  jz      short loc_180001ED7
0x180001ec7  mov     rax, rdx
0x180001eca  inc     rax
0x180001ecd  cmp     [rcx+rax], dil
0x180001ed1  jnz     short loc_180001ECA
0x180001ed3  inc     eax
0x180001ed5  jmp     short loc_180001EDD
0x180001ed7  mov     rcx, rsi
0x180001eda  mov     eax, r8d
0x180001edd  mov     [rbp+0A0h+var_108], eax
0x180001ee0  mov     rax, [rbp+0A0h+arg_38]
0x180001ee7  mov     [rbp+0A0h+var_120], rax
0x180001eeb  mov     rax, [rbp+0A0h+arg_30]
0x180001ef2  mov     [rbp+0A0h+var_110], rcx
0x180001ef6  mov     [rbp+0A0h+var_104], edi
0x180001ef9  mov     [rbp+0A0h+var_118], 4
0x180001f01  mov     rcx, [rax]
0x180001f04  test    rcx, rcx
0x180001f07  jz      short loc_180001F18
0x180001f09  inc     rdx
0x180001f0c  cmp     [rcx+rdx], dil
0x180001f10  jnz     short loc_180001F09
0x180001f12  lea     r8d, [rdx+1]
0x180001f16  jmp     short loc_180001F1B
0x180001f18  mov     rcx, rsi
0x180001f1b  mov     rax, [rbp+0A0h+arg_28]
0x180001f22  xor     r9d, r9d; int
0x180001f25  mov     [rsp+1A0h+var_140], rax
0x180001f2a  mov     rdx, r11; int
0x180001f2d  mov     rax, [rbp+0A0h+arg_20]
0x180001f34  mov     [rsp+1A0h+var_150], rax
0x180001f39  lea     rax, [rsp+1A0h+var_170]
0x180001f3e  mov     [rsp+1A0h+var_130], rcx
0x180001f43  mov     rcx, r10; int
0x180001f46  mov     [rsp+1A0h+var_128], r8d
0x180001f4b  mov     r8, rbx; int
0x180001f4e  mov     [rsp+1A0h+var_178], rax; PEVENT_DATA_DESCRIPTOR
0x180001f53  mov     [rsp+1A0h+var_180], 14h; ULONG
0x180001f5b  mov     [rsp+1A0h+var_124], edi
0x180001f5f  mov     [rsp+1A0h+var_138], 4
0x180001f68  mov     [rsp+1A0h+var_148], 8
0x180001f71  call    _tlgWriteTransfer_EventWriteTransfer
0x180001f76  mov     rcx, [rbp+0A0h+var_30]
0x180001f7a  xor     rcx, rsp; StackCookie
0x180001f7d  call    __security_check_cookie
0x180001f82  add     rsp, 180h
0x180001f89  pop     r15
0x180001f8b  pop     rdi
0x180001f8c  pop     rsi
0x180001f8d  pop     rbx
0x180001f8e  pop     rbp
0x180001f8f  retn
```
