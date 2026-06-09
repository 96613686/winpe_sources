# CTouchSelectionHandle::RenderHandle(HDC__ *,bool,ulong,ulong)

- ea: `0x1801fea58`
- end: `0x1801fec09`
- name: `?RenderHandle@CTouchSelectionHandle@@IEBAXPEAUHDC__@@_NKK@Z`
- size: `433`
- prototype: `void __usercall(CTouchSelectionHandle *__hidden this@<rcx>, HDC@<rdx>, bool@<r8b>, unsigned int@<r9d>, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1801fb7e0`
- `0x1801ffbe8`

## callees

- `0x18013bad0`
- `0x18013c916`
- `0x1801fad58`
- `0x1801fb550`
- `0x1801fb5fc`
- `0x1801fea58`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801feab6`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801febd3`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801feab6`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801febd3`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkMode` at `0x1801feb12`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkMode` at `0x1801feb12`
- `ext-ms-win-gdi-font-l1-1-1!SetTextAlign` at `0x1801feb20`
- `ext-ms-win-gdi-font-l1-1-1!SetTextAlign` at `0x1801feb20`
- `ext-ms-win-gdi-font-l1-1-1!GetOutlineTextMetricsW` at `0x1801feb04`
- `ext-ms-win-gdi-font-l1-1-1!GetOutlineTextMetricsW` at `0x1801feb04`
- `ext-ms-win-gdi-font-l1-1-1!GetCharABCWidthsW` at `0x1801feadf`
- `ext-ms-win-gdi-font-l1-1-1!GetCharABCWidthsW` at `0x1801feadf`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801febdc`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801febdc`

## pseudocode

```c
void __fastcall CTouchSelectionHandle::RenderHandle(
        CTouchSelectionHandle *this,
        HDC a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5)
{
  __int64 v5; // rax
  int v9; // ebx
  int v10; // r15d
  HFONT GripperFont; // r14
  HGDIOBJ v12; // r12
  int v13[4]; // [rsp+50h] [rbp-B0h] BYREF
  _OUTLINETEXTMETRICW potm; // [rsp+60h] [rbp-A0h] BYREF
  __int128 ABC; // [rsp+150h] [rbp+50h] BYREF
  int v16[4]; // [rsp+160h] [rbp+60h]
  int v17; // [rsp+170h] [rbp+70h]

  v5 = *((_QWORD *)this + 16);
  v13[0] = 0;
  v9 = *(_DWORD *)(v5 + 24);
  v10 = *(_DWORD *)(v5 + 8);
  GripperFont = CTouchSelectionHandle::CreateGripperFont(this, v9, v13);
  v12 = SelectObject(a2, GripperFont);
  ABC = 0;
  v17 = 0;
  *(_OWORD *)v16 = 0;
  GetCharABCWidthsW(a2, 0xE2A0u, 0xE2A2u, (LPABC)&ABC);
  memset_0(&potm, 0, sizeof(potm));
  GetOutlineTextMetricsW(a2, 0xE8u, &potm);
  SetBkMode(a2, 1);
  SetTextAlign(a2, 0x18u);
  CTouchSelectionHandle::DrawGripperGlyph(this, a2, a5, &byte_1802BF3A8, v10, v9, v9, SHIDWORD(ABC), v16[0]);
  CTouchSelectionHandle::DrawGripperGlyph(this, a2, a4, &dword_1802BF3AC, v10, v9, v9, ABC, SDWORD1(ABC));
  if ( *((_BYTE *)this + 113) )
    CTouchSelectionHandle::DrawPost(
      this,
      a2,
      a4,
      v16[3],
      v10,
      (int)(float)((float)((float)(v16[0] - DWORD1(ABC)) * 0.5) + 0.5));
  SelectObject(a2, v12);
  DeleteObject(GripperFont);
}

```

## disassembly

```asm
0x1801fea58  mov     [rsp-8+arg_10], rbx
0x1801fea5d  push    rbp
0x1801fea5e  push    rsi
0x1801fea5f  push    rdi
0x1801fea60  push    r12
0x1801fea62  push    r13
0x1801fea64  push    r14
0x1801fea66  push    r15
0x1801fea68  lea     rbp, [rsp-80h]
0x1801fea6d  sub     rsp, 180h
0x1801fea74  mov     rax, cs:__security_cookie
0x1801fea7b  xor     rax, rsp
0x1801fea7e  mov     [rbp+0B0h+var_38], rax
0x1801fea82  mov     rax, [rcx+80h]
0x1801fea89  lea     r8, [rsp+1B0h+var_160]; int *
0x1801fea8e  mov     rdi, rdx
0x1801fea91  mov     [rsp+1B0h+var_160], 0
0x1801fea99  mov     r13d, r9d
0x1801fea9c  mov     rsi, rcx
0x1801fea9f  mov     ebx, [rax+18h]
0x1801feaa2  mov     edx, ebx; int
0x1801feaa4  mov     r15d, [rax+8]
0x1801feaa8  call    ?CreateGripperFont@CTouchSelectionHandle@@IEBAPEAUHFONT__@@HPEAH@Z; CTouchSelectionHandle::CreateGripperFont(int,int *)
0x1801feaad  mov     rdx, rax; h
0x1801feab0  mov     rcx, rdi; hdc
0x1801feab3  mov     r14, rax
0x1801feab6  call    cs:__imp_SelectObject
0x1801feabc  xorps   xmm0, xmm0
0x1801feabf  lea     r9, [rbp+0B0h+ABC]; lpABC
0x1801feac3  mov     edx, 0E2A0h; wFirst
0x1801feac8  mov     r12, rax
0x1801feacb  xor     eax, eax
0x1801feacd  mov     rcx, rdi; hdc
0x1801fead0  movups  [rbp+0B0h+ABC], xmm0
0x1801fead4  mov     [rbp+0B0h+var_40], eax
0x1801fead7  lea     r8d, [rdx+2]; wLast
0x1801feadb  movups  xmmword ptr [rbp+0B0h+var_50], xmm0
0x1801feadf  call    cs:__imp_GetCharABCWidthsW
0x1801feae5  xor     edx, edx; Val
0x1801feae7  lea     rcx, [rsp+1B0h+potm]; void *
0x1801feaec  mov     r8d, 0E8h; Size
0x1801feaf2  call    memset_0
0x1801feaf7  lea     r8, [rsp+1B0h+potm]; potm
0x1801feafc  mov     edx, 0E8h; cjCopy
0x1801feb01  mov     rcx, rdi; hdc
0x1801feb04  call    cs:__imp_GetOutlineTextMetricsW
0x1801feb0a  mov     edx, 1; mode
0x1801feb0f  mov     rcx, rdi; hdc
0x1801feb12  call    cs:__imp_SetBkMode
0x1801feb18  mov     edx, 18h; align
0x1801feb1d  mov     rcx, rdi; hdc
0x1801feb20  call    cs:__imp_SetTextAlign
0x1801feb26  mov     eax, [rbp+0B0h+var_50]
0x1801feb29  lea     r9, byte_1802BF3A8; unsigned __int16 *
0x1801feb30  mov     r8d, [rbp+0B0h+arg_20]; unsigned int
0x1801feb37  mov     rdx, rdi; HDC
0x1801feb3a  mov     [rsp+1B0h+var_170], eax; int
0x1801feb3e  mov     rcx, rsi; this
0x1801feb41  mov     eax, dword ptr [rbp+0B0h+ABC+0Ch]
0x1801feb44  mov     [rsp+1B0h+var_178], eax; int
0x1801feb48  mov     [rsp+1B0h+var_180], ebx; int
0x1801feb4c  mov     [rsp+1B0h+var_188], ebx; int
0x1801feb50  mov     [rsp+1B0h+var_190], r15d; int
0x1801feb55  call    ?DrawGripperGlyph@CTouchSelectionHandle@@IEBAXPEAUHDC__@@KPEBGHHHHH@Z; CTouchSelectionHandle::DrawGripperGlyph(HDC__ *,ulong,ushort const *,int,int,int,int,int)
0x1801feb5a  mov     eax, dword ptr [rbp+0B0h+ABC+4]
0x1801feb5d  lea     r9, dword_1802BF3AC; unsigned __int16 *
0x1801feb64  mov     [rsp+1B0h+var_170], eax; int
0x1801feb68  mov     r8d, r13d; unsigned int
0x1801feb6b  mov     eax, dword ptr [rbp+0B0h+ABC]
0x1801feb6e  mov     rdx, rdi; HDC
0x1801feb71  mov     [rsp+1B0h+var_178], eax; int
0x1801feb75  mov     rcx, rsi; this
0x1801feb78  mov     [rsp+1B0h+var_180], ebx; int
0x1801feb7c  mov     [rsp+1B0h+var_188], ebx; int
0x1801feb80  mov     [rsp+1B0h+var_190], r15d; int
0x1801feb85  call    ?DrawGripperGlyph@CTouchSelectionHandle@@IEBAXPEAUHDC__@@KPEBGHHHHH@Z; CTouchSelectionHandle::DrawGripperGlyph(HDC__ *,ulong,ushort const *,int,int,int,int,int)
0x1801feb8a  cmp     byte ptr [rsi+71h], 0
0x1801feb8e  jz      short loc_1801FEBCD
0x1801feb90  mov     eax, [rbp+0B0h+var_50]
0x1801feb93  xorps   xmm1, xmm1
0x1801feb96  sub     eax, dword ptr [rbp+0B0h+ABC+4]
0x1801feb99  mov     r8d, r13d; unsigned int
0x1801feb9c  mov     r9d, [rbp+0B0h+var_50+0Ch]; int
0x1801feba0  mov     rdx, rdi; HDC
0x1801feba3  mov     rcx, rsi; this
0x1801feba6  cvtsi2ss xmm1, rax
0x1801febab  mulss   xmm1, cs:__real@3f000000
0x1801febb3  addss   xmm1, cs:__real@3f000000
0x1801febbb  cvttss2si eax, xmm1
0x1801febbf  mov     [rsp+1B0h+var_188], eax; int
0x1801febc3  mov     [rsp+1B0h+var_190], r15d; int
0x1801febc8  call    ?DrawPost@CTouchSelectionHandle@@IEBAXPEAUHDC__@@KHHH@Z; CTouchSelectionHandle::DrawPost(HDC__ *,ulong,int,int,int)
0x1801febcd  mov     rdx, r12; h
0x1801febd0  mov     rcx, rdi; hdc
0x1801febd3  call    cs:__imp_SelectObject
0x1801febd9  mov     rcx, r14; ho
0x1801febdc  call    cs:__imp_DeleteObject
0x1801febe2  mov     rcx, [rbp+0B0h+var_38]
0x1801febe6  xor     rcx, rsp; StackCookie
0x1801febe9  call    __security_check_cookie
0x1801febee  mov     rbx, [rsp+1B0h+arg_10]
0x1801febf6  add     rsp, 180h
0x1801febfd  pop     r15
0x1801febff  pop     r14
0x1801fec01  pop     r13
0x1801fec03  pop     r12
0x1801fec05  pop     rdi
0x1801fec06  pop     rsi
0x1801fec07  pop     rbp
0x1801fec08  retn
```
