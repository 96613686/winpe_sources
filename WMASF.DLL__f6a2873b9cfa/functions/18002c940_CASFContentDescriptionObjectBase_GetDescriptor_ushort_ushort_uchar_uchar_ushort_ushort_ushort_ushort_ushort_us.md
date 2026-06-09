# CASFContentDescriptionObjectBase::GetDescriptor(ushort,ushort *,uchar *,uchar,ushort *,ushort,ushort *,ushort *,ushort,ushort *,ushort *)

- ea: `0x18002c940`
- end: `0x18002cbf6`
- name: `?GetDescriptor@CASFContentDescriptionObjectBase@@UEAAJGPEAGPEAEE0G00G00@Z`
- size: `694`
- prototype: `__int64 __fastcall(CASFContentDescriptionObjectBase *__hidden this, unsigned __int16, unsigned __int16 *, unsigned __int8 *, char, unsigned __int16 *, unsigned __int16, unsigned __int16 *, unsigned __int16 *, unsigned __int16, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x18000ff88`
- `0x18002c6c0`
- `0x18002c940`
- `0x180030a00`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFContentDescriptionObjectBase::GetDescriptor(
        CASFContentDescriptionObjectBase *this,
        unsigned __int16 a2,
        unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned __int8 a5,
        unsigned __int16 *a6,
        unsigned __int16 a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        unsigned __int16 a10,
        unsigned __int16 *a11,
        unsigned __int16 *a12)
{
  struct IWMSCriticalSection *v15; // rdx
  int v16; // ebx
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // r11
  void *v21; // rdx
  unsigned __int16 v22; // ax
  __int64 v23; // rax
  void *v24; // rbx
  unsigned __int16 v25; // r11
  const void *v26; // rdx
  _WORD *v27; // rbx
  _BYTE v30[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v31; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v32; // [rsp+48h] [rbp-B8h]
  unsigned __int8 v33[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v34; // [rsp+52h] [rbp-AEh]
  unsigned __int16 v35; // [rsp+54h] [rbp-ACh]
  void *Src; // [rsp+58h] [rbp-A8h]
  void *v37; // [rsp+60h] [rbp-A0h]
  __int64 v38; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v39[256]; // [rsp+70h] [rbp-90h] BYREF

  v15 = (struct IWMSCriticalSection *)*((_QWORD *)this + 4);
  v32 = a6;
  v31 = a11;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v30, v15);
  if ( !*((_QWORD *)this + 5) )
  {
    v16 = -1072887818;
LABEL_36:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v30);
    return (unsigned int)v16;
  }
  if ( a3 && a4 && a6 && (a8 || !a7) && a9 && (v31 || !a10) && a12 )
  {
    if ( (unsigned int)a2 >= *((_DWORD *)this + 158) )
    {
      v16 = -1072887824;
      goto LABEL_36;
    }
    CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[]((char *)this + 80, v33, a2);
    *a3 = v35;
    *a4 = v33[0];
    v17 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
    v38 = 0;
    v16 = ASFFindHeaderObject(
            v17,
            (__int64)&CLSID_ASFLanguageListObject,
            (__int64)&IID_IASFLanguageListObject,
            (__int64)&v38);
    if ( v16 < 0 )
      goto LABEL_36;
    LOBYTE(v18) = -1;
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, unsigned __int16 *))(*(_QWORD *)v38 + 104LL))(
            v38,
            v34,
            v18,
            v39);
    if ( v38 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      v38 = 0;
    }
    if ( v16 < 0 )
      goto LABEL_36;
    v19 = -1;
    do
      ++v19;
    while ( v39[v19] );
    if ( a5 < (unsigned __int64)(v19 + 1) )
      goto LABEL_35;
    StringCchCopyW(v32, a5, v39);
    v21 = Src;
    if ( Src )
    {
      v23 = v20;
      do
        ++v23;
      while ( *((_WORD *)Src + v23) );
      v22 = v23 + 1;
    }
    else
    {
      v22 = 1;
    }
    *a9 = v22;
    v24 = v37;
    do
      ++v20;
    while ( *((_WORD *)v37 + v20) );
    v25 = v20 + 1;
    *a12 = v25;
    if ( a7 < *a9 || a10 < v25 )
    {
LABEL_35:
      v16 = -1072887855;
      goto LABEL_36;
    }
    if ( v21 )
    {
      memcpy_0(a8, v21, 2LL * *a9);
      a8[*a9 - 1] = 0;
    }
    else if ( a7 )
    {
      *a9 = 1;
      *a8 = 0;
    }
    v26 = v24;
    v27 = v31;
    memcpy_0(v31, v26, 2LL * *a12);
    v27[*a12 - 1] = 0;
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v30);
    return 0;
  }
  else
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v30);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18002c940  push    rbp
0x18002c942  push    rbx
0x18002c943  push    rsi
0x18002c944  push    rdi
0x18002c945  push    r12
0x18002c947  push    r13
0x18002c949  push    r14
0x18002c94b  push    r15
0x18002c94d  lea     rbp, [rsp-188h]
0x18002c955  sub     rsp, 288h
0x18002c95c  mov     rax, cs:__security_cookie
0x18002c963  xor     rax, rsp
0x18002c966  mov     [rbp+1C0h+var_50], rax
0x18002c96d  mov     rax, [rbp+1C0h+arg_50]
0x18002c974  mov     rbx, rcx
0x18002c977  mov     rsi, [rbp+1C0h+arg_28]
0x18002c97e  mov     r12, r9
0x18002c981  mov     r14, [rbp+1C0h+arg_38]
0x18002c988  mov     r15, r8
0x18002c98b  mov     rdi, [rbp+1C0h+arg_40]
0x18002c992  mov     r13, [rbp+1C0h+arg_58]
0x18002c999  mov     [rsp+2C0h+var_290], dx
0x18002c99e  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002c9a2  lea     rcx, [rsp+2C0h+var_288]; this
0x18002c9a7  mov     [rsp+2C0h+var_278], rsi
0x18002c9ac  mov     [rsp+2C0h+var_280], rax
0x18002c9b1  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002c9b6  cmp     qword ptr [rbx+28h], 0
0x18002c9bb  jnz     short loc_18002C9C7
0x18002c9bd  mov     ebx, 0C00D07F6h
0x18002c9c2  jmp     loc_18002CBB6
0x18002c9c7  test    r15, r15
0x18002c9ca  jz      loc_18002CBC4
0x18002c9d0  test    r12, r12
0x18002c9d3  jz      loc_18002CBC4
0x18002c9d9  test    rsi, rsi
0x18002c9dc  jz      loc_18002CBC4
0x18002c9e2  movzx   esi, [rbp+1C0h+arg_30]
0x18002c9e9  test    r14, r14
0x18002c9ec  jnz     short loc_18002C9F9
0x18002c9ee  xor     eax, eax
0x18002c9f0  cmp     ax, si
0x18002c9f3  jnz     loc_18002CBC4
0x18002c9f9  test    rdi, rdi
0x18002c9fc  jz      loc_18002CBC4
0x18002ca02  cmp     [rsp+2C0h+var_280], 0
0x18002ca08  jnz     short loc_18002CA19
0x18002ca0a  xor     eax, eax
0x18002ca0c  cmp     ax, [rbp+1C0h+arg_48]
0x18002ca13  jnz     loc_18002CBC4
0x18002ca19  test    r13, r13
0x18002ca1c  jz      loc_18002CBC4
0x18002ca22  movzx   r8d, [rsp+2C0h+var_290]
0x18002ca28  lea     rcx, [rbx+50h]
0x18002ca2c  cmp     r8d, [rcx+228h]
0x18002ca33  jb      short loc_18002CA3F
0x18002ca35  mov     ebx, 0C00D07F0h
0x18002ca3a  jmp     loc_18002CBB6
0x18002ca3f  lea     rdx, [rsp+2C0h+var_270]
0x18002ca44  call    ??A?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEBA?AUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@K@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](ulong)
0x18002ca49  movzx   eax, [rsp+2C0h+var_26C]
0x18002ca4e  lea     r9, [rsp+2C0h+var_258]
0x18002ca53  mov     [r15], ax
0x18002ca57  lea     r8, IID_IASFLanguageListObject
0x18002ca5e  mov     al, [rsp+2C0h+var_270]
0x18002ca62  lea     rdx, CLSID_ASFLanguageListObject
0x18002ca69  mov     [r12], al
0x18002ca6d  xor     r15d, r15d
0x18002ca70  mov     rcx, [rbx+28h]
0x18002ca74  mov     [rsp+2C0h+var_258], r15
0x18002ca79  call    ASFFindHeaderObject
0x18002ca7e  mov     ebx, eax
0x18002ca80  test    eax, eax
0x18002ca82  js      loc_18002CBB6
0x18002ca88  mov     rcx, [rsp+2C0h+var_258]
0x18002ca8d  lea     r9, [rsp+2C0h+var_250]
0x18002ca92  movzx   edx, [rsp+2C0h+var_26E]
0x18002ca97  mov     r8b, 0FFh
0x18002ca9a  mov     rax, [rcx]
0x18002ca9d  mov     rax, [rax+68h]
0x18002caa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002caa6  mov     rcx, [rsp+2C0h+var_258]
0x18002caab  mov     ebx, eax
0x18002caad  test    rcx, rcx
0x18002cab0  jz      short loc_18002CAC3
0x18002cab2  mov     rax, [rcx]
0x18002cab5  mov     rax, [rax+10h]
0x18002cab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cabe  mov     [rsp+2C0h+var_258], r15
0x18002cac3  test    ebx, ebx
0x18002cac5  js      loc_18002CBB6
0x18002cacb  movzx   edx, [rbp+1C0h+arg_20]; unsigned __int64
0x18002cad2  lea     rcx, [rsp+2C0h+var_250]
0x18002cad7  or      r11, 0FFFFFFFFFFFFFFFFh
0x18002cadb  mov     rax, r11
0x18002cade  inc     rax
0x18002cae1  cmp     [rcx+rax*2], r15w
0x18002cae6  jnz     short loc_18002CADE
0x18002cae8  inc     rax
0x18002caeb  cmp     rdx, rax
0x18002caee  jb      loc_18002CBB1
0x18002caf4  mov     rcx, [rsp+2C0h+var_278]; unsigned __int16 *
0x18002caf9  lea     r8, [rsp+2C0h+var_250]; unsigned __int16 *
0x18002cafe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002cb03  mov     rdx, [rsp+2C0h+Src]; Src
0x18002cb08  test    rdx, rdx
0x18002cb0b  jnz     short loc_18002CB15
0x18002cb0d  lea     ecx, [rdx+1]
0x18002cb10  movzx   eax, cx
0x18002cb13  jmp     short loc_18002CB2A
0x18002cb15  mov     rax, r11
0x18002cb18  inc     rax
0x18002cb1b  cmp     [rdx+rax*2], r15w
0x18002cb20  jnz     short loc_18002CB18
0x18002cb22  mov     ecx, 1
0x18002cb27  add     ax, cx
0x18002cb2a  mov     [rdi], ax
0x18002cb2d  mov     rbx, [rsp+2C0h+var_260]
0x18002cb32  inc     r11
0x18002cb35  cmp     [rbx+r11*2], r15w
0x18002cb3a  jnz     short loc_18002CB32
0x18002cb3c  add     r11w, cx
0x18002cb40  mov     [r13+0], r11w
0x18002cb45  cmp     si, [rdi]
0x18002cb48  jb      short loc_18002CBB1
0x18002cb4a  cmp     [rbp+1C0h+arg_48], r11w
0x18002cb52  jb      short loc_18002CBB1
0x18002cb54  test    rdx, rdx
0x18002cb57  jz      short loc_18002CB73
0x18002cb59  movzx   r8d, word ptr [rdi]
0x18002cb5d  mov     rcx, r14; void *
0x18002cb60  add     r8, r8; Size
0x18002cb63  call    memcpy_0
0x18002cb68  movzx   ecx, word ptr [rdi]
0x18002cb6b  mov     [r14+rcx*2-2], r15w
0x18002cb71  jmp     short loc_18002CB80
0x18002cb73  cmp     r15w, si
0x18002cb77  jz      short loc_18002CB80
0x18002cb79  mov     [rdi], cx
0x18002cb7c  mov     [r14], r15w
0x18002cb80  movzx   r8d, word ptr [r13+0]
0x18002cb85  mov     rdx, rbx; Src
0x18002cb88  mov     rbx, [rsp+2C0h+var_280]
0x18002cb8d  add     r8, r8; Size
0x18002cb90  mov     rcx, rbx; void *
0x18002cb93  call    memcpy_0
0x18002cb98  movzx   ecx, word ptr [r13+0]
0x18002cb9d  mov     [rbx+rcx*2-2], r15w
0x18002cba3  lea     rcx, [rsp+2C0h+var_288]; this
0x18002cba8  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002cbad  xor     eax, eax
0x18002cbaf  jmp     short loc_18002CBD3
0x18002cbb1  mov     ebx, 0C00D07D1h
0x18002cbb6  lea     rcx, [rsp+2C0h+var_288]; this
0x18002cbbb  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002cbc0  mov     eax, ebx
0x18002cbc2  jmp     short loc_18002CBD3
0x18002cbc4  lea     rcx, [rsp+2C0h+var_288]; this
0x18002cbc9  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002cbce  mov     eax, 80070057h
0x18002cbd3  mov     rcx, [rbp+1C0h+var_50]
0x18002cbda  xor     rcx, rsp; StackCookie
0x18002cbdd  call    __security_check_cookie
0x18002cbe2  add     rsp, 288h
0x18002cbe9  pop     r15
0x18002cbeb  pop     r14
0x18002cbed  pop     r13
0x18002cbef  pop     r12
0x18002cbf1  pop     rdi
0x18002cbf2  pop     rsi
0x18002cbf3  pop     rbx
0x18002cbf4  pop     rbp
0x18002cbf5  retn
```
