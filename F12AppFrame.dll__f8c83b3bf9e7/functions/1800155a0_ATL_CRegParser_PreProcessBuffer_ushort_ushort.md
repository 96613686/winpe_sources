# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800155a0`
- end: `0x180015858`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `696`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015acc`

## callees

- `0x180001800`
- `0x180003858`
- `0x180006e00`
- `0x180013050`
- `0x1800155a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800156e1`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800156e1`
- `KERNEL32!lstrcmpiW` at `0x18001572b`
- `KERNEL32!lstrcmpiW` at `0x18001572b`
- `ole32!CoTaskMemAlloc` at `0x18001562c`
- `ole32!CoTaskMemAlloc` at `0x18001562c`
- `ole32!CoTaskMemFree` at `0x18001564a`
- `ole32!CoTaskMemFree` at `0x1800157e7`
- `ole32!CoTaskMemFree` at `0x18001564a`
- `ole32!CoTaskMemFree` at `0x1800157e7`
- `USER32!CharNextW` at `0x180015676`
- `USER32!CharNextW` at `0x1800156a7`
- `USER32!CharNextW` at `0x180015794`
- `USER32!CharNextW` at `0x1800157bd`
- `USER32!CharNextW` at `0x180015676`
- `USER32!CharNextW` at `0x1800156a7`
- `USER32!CharNextW` at `0x180015794`
- `USER32!CharNextW` at `0x1800157bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdx
  WCHAR v12; // ax
  LPWSTR v13; // rax
  WCHAR v14; // cx
  const unsigned __int16 *v15; // rdx
  const WCHAR *v16; // rsi
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rdi
  int v20; // ebx
  int v21; // edx
  unsigned int v22; // r8d
  unsigned int v23; // ebx
  const unsigned __int16 *v24; // rdx
  __int64 v25; // r8
  const WCHAR *i; // rax
  _DWORD v27[2]; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v29; // [rsp+30h] [rbp-29h]
  WCHAR String2[32]; // [rsp+40h] [rbp-19h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  if ( v7 < 100 )
    v7 = 1000;
  v27[0] = 0;
  v27[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v8);
    v10 = v9;
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    v10 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_50:
    v23 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_51;
  }
  while ( 1 )
  {
    if ( v12 != 37 )
    {
      v15 = v4;
LABEL_47:
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v15, 1) )
        break;
      goto LABEL_48;
    }
    v13 = CharNextW(v4);
    *(_QWORD *)this = v13;
    v14 = *v13;
    if ( *v13 == 37 )
    {
      v15 = v13;
      goto LABEL_47;
    }
    if ( !v13 )
      goto LABEL_34;
    v16 = 0;
    while ( v14 )
    {
      if ( v14 == 37 )
      {
        v16 = v13;
        break;
      }
      v13 = CharNextW(v13);
      v14 = *v13;
    }
    if ( !v16 )
    {
LABEL_34:
      v23 = -2147352567;
      goto LABEL_51;
    }
    v17 = ((__int64)v16 - *(_QWORD *)this) >> 1;
    if ( v17 > 31 )
    {
      v23 = -2147467259;
      goto LABEL_51;
    }
    v18 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v17);
    if ( v18 )
    {
      if ( v18 == 12 )
        ATL::AtlThrowImpl(-2147024882);
      if ( v18 == 22 || v18 == 34 )
        ATL::AtlThrowImpl(-2147024809);
      if ( v18 != 80 )
        ATL::AtlThrowImpl(-2147467259);
    }
    v19 = *((_QWORD *)this + 1);
    v20 = 0;
    if ( *(int *)(v19 + 24) <= 0 )
      goto LABEL_34;
    while ( lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)(v19 + 8) + 8LL * v20), String2) )
    {
      if ( ++v20 >= *(_DWORD *)(v19 + 24) )
        goto LABEL_34;
    }
    if ( v20 == -1 )
      goto LABEL_34;
    if ( v20 < 0 || v20 >= *(_DWORD *)(v19 + 24) )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, v21, v22);
      __debugbreak();
    }
    v24 = *(const unsigned __int16 **)(*(_QWORD *)(v19 + 16) + 8LL * v20);
    if ( !v24 )
      goto LABEL_34;
    v29 = 0;
    v25 = -1;
    do
      ++v25;
    while ( v24[v25] );
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v24, v25) )
      break;
    for ( i = *(const WCHAR **)this; i != v16; *(_QWORD *)this = i )
      i = CharNextW(i);
LABEL_48:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (unsigned __int16 *)pv;
      goto LABEL_50;
    }
  }
  v23 = -2147024882;
LABEL_51:
  CoTaskMemFree(pv);
  return v23;
}

```

## disassembly

```asm
0x1800155a0  mov     [rsp-8+arg_8], rbx
0x1800155a5  mov     [rsp-8+arg_18], rsi
0x1800155aa  push    rbp
0x1800155ab  push    rdi
0x1800155ac  push    r12
0x1800155ae  push    r14
0x1800155b0  push    r15
0x1800155b2  lea     rbp, [rsp-37h]
0x1800155b7  sub     rsp, 90h
0x1800155be  mov     rax, cs:__security_cookie
0x1800155c5  xor     rax, rsp
0x1800155c8  mov     [rbp+57h+var_30], rax
0x1800155cc  mov     r15, r8
0x1800155cf  mov     rbx, rdx
0x1800155d2  mov     r14, rcx
0x1800155d5  xor     r12d, r12d
0x1800155d8  test    rdx, rdx
0x1800155db  jz      loc_1800157FF
0x1800155e1  test    r8, r8
0x1800155e4  jz      loc_1800157FF
0x1800155ea  mov     [r8], r12
0x1800155ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800155f1  inc     rax
0x1800155f4  cmp     [rdx+rax*2], r12w
0x1800155f9  jnz     short loc_1800155F1
0x1800155fb  add     eax, eax
0x1800155fd  mov     ecx, 3E8h
0x180015602  cmp     eax, 64h ; 'd'
0x180015605  cmovl   eax, ecx
0x180015608  mov     [rbp+57h+var_90], r12d
0x18001560c  mov     [rbp+57h+var_8C], eax
0x18001560f  mov     ecx, eax
0x180015611  add     rcx, rcx
0x180015614  mov     eax, 0FFFFFFFFh
0x180015619  cmp     rcx, rax
0x18001561c  jbe     short loc_18001562A
0x18001561e  mov     rax, r12
0x180015621  mov     rdx, r12
0x180015624  mov     [rbp+57h+pv], rdx
0x180015628  jmp     short loc_180015642
0x18001562a  mov     ecx, ecx; cb
0x18001562c  call    cs:__imp_CoTaskMemAlloc
0x180015632  mov     rdx, rax
0x180015635  mov     [rbp+57h+pv], rax
0x180015639  test    rax, rax
0x18001563c  jz      short loc_180015642
0x18001563e  mov     [rax], r12w
0x180015642  test    rax, rax
0x180015645  jnz     short loc_18001565A
0x180015647  mov     rcx, rax; pv
0x18001564a  call    cs:__imp_CoTaskMemFree
0x180015650  mov     eax, 8007000Eh
0x180015655  jmp     loc_180015804
0x18001565a  mov     [r14], rbx
0x18001565d  movzx   eax, word ptr [rbx]
0x180015660  test    ax, ax
0x180015663  jz      loc_1800157D9
0x180015669  cmp     ax, 25h ; '%'
0x18001566d  jnz     loc_1800157A4
0x180015673  mov     rcx, rbx; lpsz
0x180015676  call    cs:__imp_CharNextW
0x18001567c  mov     [r14], rax
0x18001567f  movzx   ecx, word ptr [rax]
0x180015682  cmp     cx, 25h ; '%'
0x180015686  jnz     short loc_180015690
0x180015688  mov     rdx, rax
0x18001568b  jmp     loc_1800157A7
0x180015690  test    rax, rax
0x180015693  jz      loc_18001573C
0x180015699  mov     rsi, r12
0x18001569c  jmp     short loc_1800156B0
0x18001569e  cmp     cx, 25h ; '%'
0x1800156a2  jz      short loc_1800156B7
0x1800156a4  mov     rcx, rax; lpsz
0x1800156a7  call    cs:__imp_CharNextW
0x1800156ad  movzx   ecx, word ptr [rax]
0x1800156b0  test    cx, cx
0x1800156b3  jnz     short loc_18001569E
0x1800156b5  jmp     short loc_1800156BA
0x1800156b7  mov     rsi, rax
0x1800156ba  test    rsi, rsi
0x1800156bd  jz      short loc_18001573C
0x1800156bf  mov     rax, rsi
0x1800156c2  sub     rax, [r14]
0x1800156c5  sar     rax, 1
0x1800156c8  cmp     rax, 1Fh
0x1800156cc  jg      loc_1800157F1
0x1800156d2  movsxd  r9, eax
0x1800156d5  mov     r8, [r14]
0x1800156d8  mov     edx, 20h ; ' '
0x1800156dd  lea     rcx, [rbp+57h+String2]
0x1800156e1  call    cs:__imp__o_wcsncpy_s
0x1800156e7  test    eax, eax
0x1800156e9  jz      short loc_18001570F
0x1800156eb  cmp     eax, 0Ch
0x1800156ee  jz      loc_18001584D
0x1800156f4  cmp     eax, 16h
0x1800156f7  jz      loc_180015842
0x1800156fd  cmp     eax, 22h ; '"'
0x180015700  jz      loc_180015842
0x180015706  cmp     eax, 50h ; 'P'
0x180015709  jnz     loc_180015837
0x18001570f  mov     rdi, [r14+8]
0x180015713  mov     ebx, r12d
0x180015716  cmp     [rdi+18h], r12d
0x18001571a  jle     short loc_18001573C
0x18001571c  movsxd  rax, ebx
0x18001571f  mov     rcx, [rdi+8]
0x180015723  lea     rdx, [rbp+57h+String2]; lpString2
0x180015727  mov     rcx, [rcx+rax*8]; lpString1
0x18001572b  call    cs:__imp_lstrcmpiW
0x180015731  test    eax, eax
0x180015733  jz      short loc_180015746
0x180015735  inc     ebx
0x180015737  cmp     ebx, [rdi+18h]
0x18001573a  jl      short loc_18001571C
0x18001573c  mov     ebx, 80020009h
0x180015741  jmp     loc_1800157E3
0x180015746  cmp     ebx, 0FFFFFFFFh
0x180015749  jz      short loc_18001573C
0x18001574b  test    ebx, ebx
0x18001574d  js      loc_18001582C
0x180015753  cmp     ebx, [rdi+18h]
0x180015756  jge     loc_18001582C
0x18001575c  movsxd  rcx, ebx
0x18001575f  mov     rax, [rdi+10h]
0x180015763  mov     rdx, [rax+rcx*8]; unsigned __int16 *
0x180015767  test    rdx, rdx
0x18001576a  jz      short loc_18001573C
0x18001576c  mov     [rbp+57h+var_80], r12
0x180015770  or      r8, 0FFFFFFFFFFFFFFFFh
0x180015774  inc     r8; int
0x180015777  cmp     [rdx+r8*2], r12w
0x18001577c  jnz     short loc_180015774
0x18001577e  lea     rcx, [rbp+57h+var_90]; this
0x180015782  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180015787  nop
0x180015788  test    eax, eax
0x18001578a  jz      short loc_1800157F8
0x18001578c  mov     rax, [r14]
0x18001578f  jmp     short loc_18001579D
0x180015791  mov     rcx, rax; lpsz
0x180015794  call    cs:__imp_CharNextW
0x18001579a  mov     [r14], rax
0x18001579d  cmp     rax, rsi
0x1800157a0  jnz     short loc_180015791
0x1800157a2  jmp     short loc_1800157BA
0x1800157a4  mov     rdx, rbx; unsigned __int16 *
0x1800157a7  mov     r8d, 1; int
0x1800157ad  lea     rcx, [rbp+57h+var_90]; this
0x1800157b1  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800157b6  test    eax, eax
0x1800157b8  jz      short loc_1800157F8
0x1800157ba  mov     rcx, [r14]; lpsz
0x1800157bd  call    cs:__imp_CharNextW
0x1800157c3  mov     rbx, rax
0x1800157c6  mov     [r14], rax
0x1800157c9  movzx   eax, word ptr [rax]
0x1800157cc  test    ax, ax
0x1800157cf  jnz     loc_180015669
0x1800157d5  mov     rdx, [rbp+57h+pv]
0x1800157d9  mov     ebx, r12d
0x1800157dc  mov     [rbp+57h+pv], r12
0x1800157e0  mov     [r15], rdx
0x1800157e3  mov     rcx, [rbp+57h+pv]; pv
0x1800157e7  call    cs:__imp_CoTaskMemFree
0x1800157ed  mov     eax, ebx
0x1800157ef  jmp     short loc_180015804
0x1800157f1  mov     ebx, 80004005h
0x1800157f6  jmp     short loc_1800157E3
0x1800157f8  mov     ebx, 8007000Eh
0x1800157fd  jmp     short loc_1800157E3
0x1800157ff  mov     eax, 80004003h
0x180015804  mov     rcx, [rbp+57h+var_30]
0x180015808  xor     rcx, rsp; StackCookie
0x18001580b  call    __security_check_cookie
0x180015810  lea     r11, [rsp+0B0h+var_20]
0x180015818  mov     rbx, [r11+38h]
0x18001581c  mov     rsi, [r11+48h]
0x180015820  mov     rsp, r11
0x180015823  pop     r15
0x180015825  pop     r14
0x180015827  pop     r12
0x180015829  pop     rdi
0x18001582a  pop     rbp
0x18001582b  retn
0x18001582c  mov     ecx, 0C000008Ch; this
0x180015831  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180015836  int     3; Trap to Debugger
0x180015837  mov     ecx, 80004005h; int
0x18001583c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180015842  mov     ecx, 80070057h; int
0x180015847  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001584d  mov     ecx, 8007000Eh; int
0x180015852  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
