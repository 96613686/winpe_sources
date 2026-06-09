# CopyOnWriteBitmap::CreateHICON(HICON__ * *)

- ea: `0x180006220`
- end: `0x18000649f`
- name: `?CreateHICON@CopyOnWriteBitmap@@AEAA?AW4Status@@PEAPEAUHICON__@@@Z`
- size: `639`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800d73f0`

## callees

- `0x180006220`
- `0x1800064a8`
- `0x1800067bc`
- `0x18001ec80`
- `0x180025270`
- `0x180025ae8`
- `0x1800fe680`
- `0x180169010`

## import_xrefs

- `USER32!CreateIconIndirect` at `0x18000647d`
- `USER32!CreateIconIndirect` at `0x18000647d`
- `USER32!GetDC` at `0x180006409`
- `USER32!GetDC` at `0x180006409`
- `USER32!ReleaseDC` at `0x180006494`
- `USER32!ReleaseDC` at `0x180006494`
- `GDI32!SetDIBits` at `0x18000646f`
- `GDI32!SetDIBits` at `0x18000646f`
- `GDI32!SetBkMode` at `0x180006445`
- `GDI32!SetBkMode` at `0x180006445`
- `GDI32!SetBkColor` at `0x180006437`
- `GDI32!SetBkColor` at `0x180006437`
- `GDI32!SetTextColor` at `0x180006429`
- `GDI32!SetTextColor` at `0x180006429`
- `GDI32!CreateBitmap` at `0x1800062c2`
- `GDI32!CreateBitmap` at `0x1800062c2`
- `GDI32!DeleteObject` at `0x1800062ee`
- `GDI32!DeleteObject` at `0x18000631f`
- `GDI32!DeleteObject` at `0x1800062ee`
- `GDI32!DeleteObject` at `0x18000631f`

## pseudocode

```c
void __fastcall __noreturn CopyOnWriteBitmap::CreateHICON(LONG *a1, __int64 a2)
{
  ICONINFO piconinfo; // [rsp+60h] [rbp-39h] BYREF
  __int64 v3; // [rsp+80h] [rbp-19h]

  v3 = a2;
  *(_OWORD *)&piconinfo.hbmMask = 0;
  CopyOnWriteBitmap::CreateHBITMAP(a1, &piconinfo.hbmColor, 0);
}

```

## disassembly

```asm
0x180006220  mov     [rsp-8+arg_10], rbx
0x180006225  push    rbp
0x180006226  push    rsi
0x180006227  push    rdi
0x180006228  push    r12
0x18000622a  push    r13
0x18000622c  push    r14
0x18000622e  push    r15
0x180006230  lea     rbp, [rsp-27h]
0x180006235  sub     rsp, 0C0h
0x18000623c  mov     rax, cs:__security_cookie
0x180006243  xor     rax, rsp
0x180006246  mov     [rbp+57h+var_38], rax
0x18000624a  xorps   xmm0, xmm0
0x18000624d  mov     [rbp+57h+var_70], rdx
0x180006251  mov     r13, rdx
0x180006254  mov     edi, 1
0x180006259  movups  xmmword ptr [rbp+57h+piconinfo.fIcon], xmm0
0x18000625d  xor     r8d, r8d
0x180006260  mov     [rbp+57h+piconinfo.fIcon], edi
0x180006263  lea     rdx, [rbp+57h+piconinfo.hbmColor]
0x180006267  mov     rsi, rcx
0x18000626a  movups  xmmword ptr [rbp+57h+piconinfo.hbmMask], xmm0
0x18000626e  call    ?CreateHBITMAP@CopyOnWriteBitmap@@AEAA?AW4Status@@PEAPEAUHBITMAP__@@K@Z; CopyOnWriteBitmap::CreateHBITMAP(HBITMAP__ * *,ulong)
0x180006273  mov     ebx, eax
0x180006275  test    eax, eax
0x180006277  jnz     loc_180006325
0x18000627d  xorps   xmm0, xmm0
0x180006280  lea     rax, [rbp+57h+nWidth]
0x180006284  mov     r9d, 26200Ah
0x18000628a  mov     [rsp+0F0h+lpBits], rax
0x18000628f  mov     r8d, edi
0x180006292  xor     edx, edx
0x180006294  mov     rcx, rsi
0x180006297  movups  xmmword ptr [rbp+57h+nWidth], xmm0
0x18000629b  movups  [rbp+57h+var_A0], xmm0
0x18000629f  call    ?LockBits@CopyOnWriteBitmap@@AEBA?AW4Status@@PEBVGpRect@GpRuntime@@IHPEAVBitmapData@@@Z; CopyOnWriteBitmap::LockBits(GpRuntime::GpRect const *,uint,int,BitmapData *)
0x1800062a4  mov     ebx, eax
0x1800062a6  test    eax, eax
0x1800062a8  jnz     short loc_18000631B
0x1800062aa  mov     edx, [rbp+57h+nWidth+4]; nHeight
0x1800062ad  lea     ebx, [rdi+6]
0x1800062b0  mov     ecx, [rbp+57h+nWidth]; nWidth
0x1800062b3  mov     r9d, edi; nBitCount
0x1800062b6  mov     r8d, edi; nPlanes
0x1800062b9  mov     [rsp+0F0h+lpBits], 0; lpBits
0x1800062c2  call    cs:__imp_CreateBitmap
0x1800062c8  mov     [rbp+57h+piconinfo.hbmMask], rax
0x1800062cc  test    rax, rax
0x1800062cf  jz      short loc_1800062F4
0x1800062d1  mov     ecx, [rbp+57h+nWidth]
0x1800062d4  mov     edx, 0FFFFFFFFh
0x1800062d9  mov     eax, [rbp+57h+nWidth+4]
0x1800062dc  imul    rcx, rax
0x1800062e0  cmp     rcx, rdx
0x1800062e3  jbe     short loc_18000634E
0x1800062e5  mov     ebx, 3
0x1800062ea  mov     rcx, [rbp+57h+piconinfo.hbmMask]; ho
0x1800062ee  call    cs:__imp_DeleteObject
0x1800062f4  mov     rcx, [rsi+58h]
0x1800062f8  test    rcx, rcx
0x1800062fb  jz      short loc_18000631B
0x1800062fd  mov     rax, [rcx]
0x180006300  lea     rdx, [rbp+57h+nWidth]
0x180006304  mov     rax, [rax+30h]
0x180006308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000630d  dec     dword ptr [rsi+3Ch]
0x180006310  test    eax, eax
0x180006312  jns     short loc_18000631B
0x180006314  mov     ecx, eax
0x180006316  call    ?MapHRESULTToGpStatus@@YA?AW4Status@@J@Z; MapHRESULTToGpStatus(long)
0x18000631b  mov     rcx, [rbp+57h+piconinfo.hbmColor]; ho
0x18000631f  call    cs:__imp_DeleteObject
0x180006325  mov     eax, ebx
0x180006327  mov     rcx, [rbp+57h+var_38]
0x18000632b  xor     rcx, rsp; StackCookie
0x18000632e  call    __security_check_cookie
0x180006333  mov     rbx, [rsp+0F0h+arg_10]
0x18000633b  add     rsp, 0C0h
0x180006342  pop     r15
0x180006344  pop     r14
0x180006346  pop     r13
0x180006348  pop     r12
0x18000634a  pop     rdi
0x18000634b  pop     rsi
0x18000634c  pop     rbp
0x18000634d  retn
0x18000634e  mov     eax, ecx
0x180006350  shl     rax, 2
0x180006354  cmp     rax, rdx
0x180006357  ja      short loc_1800062E5
0x180006359  mov     ecx, eax
0x18000635b  xor     edx, edx
0x18000635d  call    GpMallocEx
0x180006362  mov     r14, rax
0x180006365  test    rax, rax
0x180006368  jz      loc_1800062E5
0x18000636e  mov     edx, [rbp+57h+nWidth]
0x180006371  mov     ecx, [rbp+57h+nWidth+4]
0x180006374  lea     r12d, ds:0[rdx*4]
0x18000637c  test    ecx, ecx
0x18000637e  jz      short loc_1800063E0
0x180006380  mov     r8, qword ptr [rbp+57h+var_A0]
0x180006384  xor     r10d, r10d
0x180006387  mov     r9, rax
0x18000638a  mov     r13d, edi
0x18000638d  xor     r15d, r15d
0x180006390  mov     r11, r8
0x180006393  mov     rdi, r9
0x180006396  test    edx, edx
0x180006398  jz      short loc_1800063C7
0x18000639a  mov     ecx, 0FF000000h
0x18000639f  mov     eax, [r11]
0x1800063a2  lea     r11, [r11+4]
0x1800063a6  and     eax, ecx
0x1800063a8  sub     eax, ecx
0x1800063aa  neg     eax
0x1800063ac  sbb     eax, eax
0x1800063ae  add     r15d, r13d
0x1800063b1  and     eax, 0FFFFFFh
0x1800063b6  mov     [rdi], eax
0x1800063b8  lea     rdi, [rdi+4]
0x1800063bc  mov     edx, [rbp+57h+nWidth]
0x1800063bf  cmp     r15d, edx
0x1800063c2  jb      short loc_18000639F
0x1800063c4  mov     ecx, [rbp+57h+nWidth+4]
0x1800063c7  movsxd  rax, [rbp+57h+nWidth+8]
0x1800063cb  add     r10d, r13d
0x1800063ce  add     r8, rax
0x1800063d1  movsxd  rax, r12d
0x1800063d4  add     r9, rax
0x1800063d7  cmp     r10d, ecx
0x1800063da  jb      short loc_18000638D
0x1800063dc  mov     r13, [rbp+57h+var_70]
0x1800063e0  neg     ecx
0x1800063e2  mov     qword ptr [rbp+57h+bmi.bmiHeader.biClrImportant], 0
0x1800063ea  mov     [rbp+57h+bmi.bmiHeader.biHeight], ecx
0x1800063ed  xorps   xmm0, xmm0
0x1800063f0  xor     ecx, ecx; hWnd
0x1800063f2  mov     [rbp+57h+bmi.bmiHeader.biSize], 28h ; '('
0x1800063f9  movdqu  xmmword ptr [rbp+57h+bmi.bmiHeader.biSizeImage], xmm0
0x1800063fe  mov     [rbp+57h+bmi.bmiHeader.biWidth], edx
0x180006401  mov     qword ptr [rbp+57h+bmi.bmiHeader.biPlanes], 200001h
0x180006409  call    cs:__imp_GetDC
0x18000640f  mov     rdi, rax
0x180006412  test    rax, rax
0x180006415  jnz     short loc_180006424
0x180006417  mov     rcx, r14
0x18000641a  call    GpFree
0x18000641f  jmp     loc_1800062EA
0x180006424  xor     edx, edx; color
0x180006426  mov     rcx, rdi; hdc
0x180006429  call    cs:__imp_SetTextColor
0x18000642f  mov     edx, 0FFFFFFh; color
0x180006434  mov     rcx, rdi; hdc
0x180006437  call    cs:__imp_SetBkColor
0x18000643d  mov     edx, 2; mode
0x180006442  mov     rcx, rdi; hdc
0x180006445  call    cs:__imp_SetBkMode
0x18000644b  mov     r9d, [rbp+57h+nWidth+4]; cLines
0x18000644f  lea     rax, [rbp+57h+bmi]
0x180006453  mov     rdx, [rbp+57h+piconinfo.hbmMask]; hbm
0x180006457  xor     r8d, r8d; start
0x18000645a  mov     [rsp+0F0h+ColorUse], 0; ColorUse
0x180006462  mov     rcx, rdi; hdc
0x180006465  mov     [rsp+0F0h+lpbmi], rax; lpbmi
0x18000646a  mov     [rsp+0F0h+lpBits], r14; lpBits
0x18000646f  call    cs:__imp_SetDIBits
0x180006475  test    eax, eax
0x180006477  jz      short loc_18000648F
0x180006479  lea     rcx, [rbp+57h+piconinfo]; piconinfo
0x18000647d  call    cs:__imp_CreateIconIndirect
0x180006483  xor     ecx, ecx
0x180006485  mov     [r13+0], rax
0x180006489  test    rax, rax
0x18000648c  cmovnz  ebx, ecx
0x18000648f  mov     rdx, rdi; hDC
0x180006492  xor     ecx, ecx; hWnd
0x180006494  call    cs:__imp_ReleaseDC
0x18000649a  jmp     loc_180006417
```
