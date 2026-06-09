# CAuthHostServer::SetFormCredential(ushort *,ushort *,ushort *,tagVARIANT *,tagVARIANT *)

- ea: `0x1400037a0`
- end: `0x1400039ef`
- name: `?SetFormCredential@CAuthHostServer@@UEAAJPEAG00PEAUtagVARIANT@@1@Z`
- size: `591`
- prototype: `int(CAuthHostServer *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140002c70`
- `0x140002c98`
- `0x1400037a0`
- `0x14000515c`
- `0x140012f16`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003962`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000382d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140003863`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400038ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400038f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000382d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140003863`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400038ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400038f6`
- `OLEAUT32!__imp_VariantCopy` at `0x140003932`
- `OLEAUT32!__imp_VariantCopy` at `0x140003944`
- `OLEAUT32!__imp_VariantCopy` at `0x140003932`
- `OLEAUT32!__imp_VariantCopy` at `0x140003944`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageW` at `0x140003958`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageW` at `0x140003958`

## pseudocode

```c
__int64 __fastcall CAuthHostServer::SetFormCredential(
        CAuthHostServer *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct tagVARIANT *pvargSrc,
        struct tagVARIANT *a6)
{
  PVOID *v10; // rcx
  VARIANTARG *v11; // rdi
  unsigned int v12; // ebx
  __int64 v13; // rbx
  __int64 v14; // rdx
  HLOCAL v15; // rax
  __int64 v16; // r8
  __int64 v17; // rdx
  HLOCAL v18; // rax
  __int64 v19; // r8
  __int64 v20; // rdx
  IRecordInfo *v21; // rax
  signed int LastError; // eax
  __int64 v23; // rdx

  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, &WPP_7c4350cd6e3a3fa521c812ffbe82d600_Traceguids);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && a3 && a4 )
  {
    if ( !*((_QWORD *)this + 2) )
      goto LABEL_32;
    v11 = (VARIANTARG *)LocalAlloc(0x40u, 0x48u);
    if ( !v11 )
      goto LABEL_10;
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    v15 = LocalAlloc(0x40u, 2 * v14 + 2);
    *(_QWORD *)&v11->vt = v15;
    if ( !v15 )
      goto LABEL_10;
    v16 = -1;
    do
      ++v16;
    while ( a2[v16] );
    memcpy_0(v15, a2, 2 * v16 + 2);
    v17 = -1;
    do
      ++v17;
    while ( a3[v17] );
    v18 = LocalAlloc(0x40u, 2 * v17 + 2);
    v11->llVal = (LONGLONG)v18;
    if ( !v18 )
      goto LABEL_10;
    v19 = -1;
    do
      ++v19;
    while ( a3[v19] );
    memcpy_0(v18, a3, 2 * v19 + 2);
    v20 = -1;
    do
      ++v20;
    while ( a4[v20] );
    v21 = (IRecordInfo *)LocalAlloc(0x40u, 2 * v20 + 2);
    v11->pRecInfo = v21;
    if ( !v21 )
    {
LABEL_10:
      v12 = -2147024882;
      goto LABEL_38;
    }
    do
      ++v13;
    while ( a4[v13] );
    memcpy_0(v21, a4, 2 * v13 + 2);
    VariantCopy(v11 + 1, pvargSrc);
    VariantCopy(v11 + 2, a6);
    if ( PostThreadMessageW(*((_DWORD *)this + 3), *((_DWORD *)this + 10), 0, (LPARAM)v11) )
    {
LABEL_32:
      v12 = 0;
      v11 = 0;
      goto LABEL_38;
    }
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v23 = 26;
LABEL_37:
      WPP_SF_d(v10[7], v23, &WPP_7c4350cd6e3a3fa521c812ffbe82d600_Traceguids, v12);
    }
  }
  else
  {
    v11 = 0;
    v12 = -2147024809;
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 68) & 2) != 0 && *((_BYTE *)v10 + 65) >= 2u )
    {
      v23 = 25;
      goto LABEL_37;
    }
  }
LABEL_38:
  FreeSetFormCredentialParam(v11);
  return v12;
}

```

## disassembly

```asm
0x1400037a0  push    rbx
0x1400037a2  push    rbp
0x1400037a3  push    rsi
0x1400037a4  push    rdi
0x1400037a5  push    r12
0x1400037a7  push    r14
0x1400037a9  push    r15
0x1400037ab  sub     rsp, 20h
0x1400037af  mov     r14, r9
0x1400037b2  mov     rbp, r8
0x1400037b5  mov     rsi, rdx
0x1400037b8  mov     r15, rcx
0x1400037bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400037c2  lea     rax, WPP_GLOBAL_Control
0x1400037c9  cmp     rcx, rax
0x1400037cc  jz      short loc_1400037FD
0x1400037ce  test    byte ptr [rcx+44h], 4
0x1400037d2  jz      short loc_1400037FD
0x1400037d4  cmp     byte ptr [rcx+41h], 5
0x1400037d8  jb      short loc_1400037FD
0x1400037da  mov     rcx, [rcx+38h]
0x1400037de  lea     r8, WPP_7c4350cd6e3a3fa521c812ffbe82d600_Traceguids
0x1400037e5  mov     edx, 18h
0x1400037ea  call    WPP_SF_
0x1400037ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400037f6  lea     rax, WPP_GLOBAL_Control
0x1400037fd  xor     r12d, r12d
0x140003800  test    rsi, rsi
0x140003803  jz      loc_1400039A5
0x140003809  test    rbp, rbp
0x14000380c  jz      loc_1400039A5
0x140003812  test    r14, r14
0x140003815  jz      loc_1400039A5
0x14000381b  cmp     [r15+10h], r12
0x14000381f  jz      loc_14000399D
0x140003825  lea     edx, [r12+48h]; uBytes
0x14000382a  lea     ecx, [rdx-8]; uFlags
0x14000382d  call    cs:__imp_LocalAlloc
0x140003833  mov     rdi, rax
0x140003836  test    rax, rax
0x140003839  jnz     short loc_140003845
0x14000383b  mov     ebx, 8007000Eh
0x140003840  jmp     loc_1400039D6
0x140003845  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140003849  mov     rdx, rbx
0x14000384c  inc     rdx
0x14000384f  cmp     [rsi+rdx*2], r12w
0x140003854  jnz     short loc_14000384C
0x140003856  lea     rdx, ds:2[rdx*2]; uBytes
0x14000385e  mov     ecx, 40h ; '@'; uFlags
0x140003863  call    cs:__imp_LocalAlloc
0x140003869  mov     [rdi], rax
0x14000386c  test    rax, rax
0x14000386f  jz      short loc_14000383B
0x140003871  mov     r8, rbx
0x140003874  inc     r8
0x140003877  cmp     [rsi+r8*2], r12w
0x14000387c  jnz     short loc_140003874
0x14000387e  lea     r8, ds:2[r8*2]; Size
0x140003886  mov     rdx, rsi; Src
0x140003889  mov     rcx, rax; void *
0x14000388c  call    memcpy_0
0x140003891  mov     rdx, rbx
0x140003894  inc     rdx
0x140003897  cmp     [rbp+rdx*2+0], r12w
0x14000389d  jnz     short loc_140003894
0x14000389f  lea     rdx, ds:2[rdx*2]; uBytes
0x1400038a7  mov     ecx, 40h ; '@'; uFlags
0x1400038ac  call    cs:__imp_LocalAlloc
0x1400038b2  mov     [rdi+8], rax
0x1400038b6  test    rax, rax
0x1400038b9  jz      short loc_14000383B
0x1400038bb  mov     r8, rbx
0x1400038be  inc     r8
0x1400038c1  cmp     [rbp+r8*2+0], r12w
0x1400038c7  jnz     short loc_1400038BE
0x1400038c9  lea     r8, ds:2[r8*2]; Size
0x1400038d1  mov     rdx, rbp; Src
0x1400038d4  mov     rcx, rax; void *
0x1400038d7  call    memcpy_0
0x1400038dc  mov     rdx, rbx
0x1400038df  inc     rdx
0x1400038e2  cmp     [r14+rdx*2], r12w
0x1400038e7  jnz     short loc_1400038DF
0x1400038e9  lea     rdx, ds:2[rdx*2]; uBytes
0x1400038f1  mov     ecx, 40h ; '@'; uFlags
0x1400038f6  call    cs:__imp_LocalAlloc
0x1400038fc  mov     [rdi+10h], rax
0x140003900  test    rax, rax
0x140003903  jz      loc_14000383B
0x140003909  inc     rbx
0x14000390c  cmp     [r14+rbx*2], r12w
0x140003911  jnz     short loc_140003909
0x140003913  lea     r8, ds:2[rbx*2]; Size
0x14000391b  mov     rdx, r14; Src
0x14000391e  mov     rcx, rax; void *
0x140003921  call    memcpy_0
0x140003926  mov     rdx, [rsp+58h+pvargSrc]; pvargSrc
0x14000392e  lea     rcx, [rdi+18h]; pvargDest
0x140003932  call    cs:__imp_VariantCopy
0x140003938  mov     rdx, [rsp+58h+arg_28]; pvargSrc
0x140003940  lea     rcx, [rdi+30h]; pvargDest
0x140003944  call    cs:__imp_VariantCopy
0x14000394a  mov     edx, [r15+28h]; Msg
0x14000394e  mov     r9, rdi; lParam
0x140003951  mov     ecx, [r15+0Ch]; idThread
0x140003955  xor     r8d, r8d; wParam
0x140003958  call    cs:__imp_PostThreadMessageW
0x14000395e  test    eax, eax
0x140003960  jnz     short loc_14000399D
0x140003962  call    cs:__imp_GetLastError
0x140003968  mov     ebx, eax
0x14000396a  test    eax, eax
0x14000396c  jle     short loc_140003977
0x14000396e  movzx   ebx, ax
0x140003971  or      ebx, 80070000h
0x140003977  mov     rcx, cs:WPP_GLOBAL_Control
0x14000397e  lea     rax, WPP_GLOBAL_Control
0x140003985  cmp     rcx, rax
0x140003988  jz      short loc_1400039D6
0x14000398a  test    byte ptr [rcx+44h], 2
0x14000398e  jz      short loc_1400039D6
0x140003990  cmp     byte ptr [rcx+41h], 2
0x140003994  jb      short loc_1400039D6
0x140003996  mov     edx, 1Ah
0x14000399b  jmp     short loc_1400039C3
0x14000399d  mov     ebx, r12d
0x1400039a0  mov     rdi, r12
0x1400039a3  jmp     short loc_1400039D6
0x1400039a5  mov     rdi, r12
0x1400039a8  mov     ebx, 80070057h
0x1400039ad  cmp     rcx, rax
0x1400039b0  jz      short loc_1400039D6
0x1400039b2  test    byte ptr [rcx+44h], 2
0x1400039b6  jz      short loc_1400039D6
0x1400039b8  cmp     byte ptr [rcx+41h], 2
0x1400039bc  jb      short loc_1400039D6
0x1400039be  mov     edx, 19h
0x1400039c3  mov     rcx, [rcx+38h]
0x1400039c7  lea     r8, WPP_7c4350cd6e3a3fa521c812ffbe82d600_Traceguids
0x1400039ce  mov     r9d, ebx
0x1400039d1  call    WPP_SF_d
0x1400039d6  mov     rcx, rdi; hMem
0x1400039d9  call    ?FreeSetFormCredentialParam@@YAXPEAU_SET_FORM_CREDENTIAL_PARAM@@@Z; FreeSetFormCredentialParam(_SET_FORM_CREDENTIAL_PARAM *)
0x1400039de  mov     eax, ebx
0x1400039e0  add     rsp, 20h
0x1400039e4  pop     r15
0x1400039e6  pop     r14
0x1400039e8  pop     r12
0x1400039ea  pop     rdi
0x1400039eb  pop     rsi
0x1400039ec  pop     rbp
0x1400039ed  pop     rbx
0x1400039ee  retn
```
