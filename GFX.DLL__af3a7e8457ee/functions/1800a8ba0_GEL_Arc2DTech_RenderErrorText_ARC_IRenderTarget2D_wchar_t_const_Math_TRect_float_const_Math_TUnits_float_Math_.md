# GEL::Arc2DTech::RenderErrorText(ARC::IRenderTarget2D &,wchar_t const *,Math::TRect<float> const &,Math::TUnits<float,Math::Points>)

- ea: `0x1800a8ba0`
- end: `0x1800a8e80`
- name: `?RenderErrorText@Arc2DTech@GEL@@CAXAEAUIRenderTarget2D@ARC@@PEB_WAEBU?$TRect@M@Math@@V?$TUnits@MUPoints@Math@@@6@@Z`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800a8f90`

## callees

- `0x18000a5e0`
- `0x18000a64c`
- `0x1800573f0`
- `0x1800a8ba0`
- `0x1800a8e80`
- `0x1800d33a4`
- `0x1801784f4`

## import_xrefs

- `mso40uiWin32Client!__imp_?MsoCreateTextFormat@DWriteAssistant@Mso@@YAJAEAUIDWriteFactory@@PEB_WPEAUIDWriteFontCollection@@W4DWRITE_FONT_WEIGHT@@W4DWRITE_FONT_STYLE@@W4DWRITE_FONT_STRETCH@@M1_NPEAPEAUIDWriteTextFormat@@@Z` at `0x1800a8d38`
- `mso40uiWin32Client!__imp_?MsoCreateTextFormat@DWriteAssistant@Mso@@YAJAEAUIDWriteFactory@@PEB_WPEAUIDWriteFontCollection@@W4DWRITE_FONT_WEIGHT@@W4DWRITE_FONT_STYLE@@W4DWRITE_FONT_STRETCH@@M1_NPEAPEAUIDWriteTextFormat@@@Z` at `0x1800a8d38`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x1800a8c00`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x1800a8c00`
- `Mso30Win32Client!__imp_MsoFLidBiDi` at `0x1800a8d59`
- `Mso30Win32Client!__imp_MsoFLidBiDi` at `0x1800a8d59`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x1800a8d51`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x1800a8d51`
- `Mso20Win32Client!__imp_?MsoGetSysColor@@YAKH@Z` at `0x1800a8c1c`
- `Mso20Win32Client!__imp_?MsoGetSysColor@@YAKH@Z` at `0x1800a8c1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GEL::Arc2DTech::RenderErrorText(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v8; // r14
  Mso::DWriteAssistant::ResourceManager *Instance; // rax
  struct IDWriteFactory *DWriteFactory; // rbx
  __int64 v11; // rdi
  unsigned int SysColor; // eax
  __int64 v13; // rax
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, bool); // rsi
  unsigned int UILcid; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 result; // rax
  __int64 v25; // [rsp+50h] [rbp-30h]
  __int64 v26; // [rsp+58h] [rbp-28h] BYREF
  float v27[4]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v28; // [rsp+B0h] [rbp+30h] BYREF

  v8 = -1;
  if ( dword_18052E508 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18052E508);
    if ( dword_18052E508 == -1 )
    {
      qword_18052E510 = (__int64)GEL::Arc2DTech::GetUIFontName();
      Init_thread_footer(&dword_18052E508);
    }
  }
  Instance = (Mso::DWriteAssistant::ResourceManager *)Mso::DWriteAssistant::ResourceManager::GetInstance();
  DWriteFactory = Mso::DWriteAssistant::ResourceManager::GetDWriteFactory(Instance);
  v11 = 0;
  v25 = 0;
  SysColor = MsoGetSysColor(8);
  v27[0] = (float)(unsigned __int8)SysColor / 255.0;
  v27[1] = (float)BYTE1(SysColor) / 255.0;
  v27[2] = (float)BYTE2(SysColor) / 255.0;
  v27[3] = 1.0;
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
  v14 = (__int64 *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 456LL))(v13, &v26);
  v15 = *v14;
  if ( *v14 )
  {
    *v14 = 0;
    v11 = v15;
    v25 = v15;
  }
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
  v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 368LL))(a1);
  (*(void (__fastcall **)(__int64, __int64, float *))(*(_QWORD *)v16 + 96LL))(v16, v11, v27);
  v28 = 0;
  v17 = Mso::DWriteAssistant::MsoCreateTextFormat(
          DWriteFactory,
          qword_18052E510,
          0,
          400,
          0,
          5,
          a4,
          L"x-none",
          1,
          &v28,
          v25);
  if ( v17 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v17, 0x121C3CCu);
    __debugbreak();
  }
  v18 = v28;
  v19 = *(__int64 (__fastcall **)(__int64, bool))(*(_QWORD *)v28 + 24LL);
  UILcid = MsoGetUILcid();
  v21 = MsoFLidBiDi(UILcid);
  v22 = v19(v18, v21 != 0);
  if ( v22 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v22, 0x121C3CDu);
    __debugbreak();
  }
  v23 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 32LL))(v28, 0);
  if ( v23 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v23, 0x121C3CEu);
    __debugbreak();
  }
  do
    ++v8;
  while ( *(_WORD *)(a2 + 2 * v8) );
  result = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int64, __int64, _DWORD, _DWORD))(*(_QWORD *)a1 + 288LL))(
             a1,
             a2,
             (unsigned int)v8,
             v28,
             a3,
             v11,
             0,
             0);
  if ( v28 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v11 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  return result;
}

```

## disassembly

```asm
0x1800a8ba0  mov     rax, rsp
0x1800a8ba3  mov     [rax+10h], rbx
0x1800a8ba7  mov     [rax+18h], rsi
0x1800a8bab  mov     [rax+20h], rdi
0x1800a8baf  push    rbp
0x1800a8bb0  push    r12
0x1800a8bb2  push    r13
0x1800a8bb4  push    r14
0x1800a8bb6  push    r15
0x1800a8bb8  mov     rbp, rsp
0x1800a8bbb  sub     rsp, 80h
0x1800a8bc2  movaps  xmmword ptr [rax-38h], xmm6
0x1800a8bc6  mov     r13, r8
0x1800a8bc9  mov     r12, rdx
0x1800a8bcc  mov     r15, rcx
0x1800a8bcf  movd    xmm6, r9d
0x1800a8bd4  mov     r9d, cs:_tls_index
0x1800a8bdb  mov     rax, gs:58h
0x1800a8be4  mov     ecx, 4
0x1800a8be9  mov     rax, [rax+r9*8]
0x1800a8bed  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800a8bf1  mov     eax, [rcx+rax]
0x1800a8bf4  cmp     cs:dword_18052E508, eax
0x1800a8bfa  jg      loc_1800A8E23
0x1800a8c00  call    cs:__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ; Mso::DWriteAssistant::ResourceManager::GetInstance(void)
0x1800a8c06  mov     rcx, rax; this
0x1800a8c09  call    ?GetDWriteFactory@ResourceManager@DWriteAssistant@Mso@@UEAAAEAUIDWriteFactory@@XZ; Mso::DWriteAssistant::ResourceManager::GetDWriteFactory(void)
0x1800a8c0e  mov     rbx, rax
0x1800a8c11  xor     esi, esi
0x1800a8c13  mov     edi, esi
0x1800a8c15  mov     [rbp+var_30], rsi
0x1800a8c19  lea     ecx, [rsi+8]
0x1800a8c1c  call    cs:__imp_?MsoGetSysColor@@YAKH@Z; MsoGetSysColor(int)
0x1800a8c22  mov     ecx, eax
0x1800a8c24  shr     ecx, 10h
0x1800a8c27  movzx   ecx, cl
0x1800a8c2a  movd    xmm3, ecx
0x1800a8c2e  cvtdq2ps xmm3, xmm3
0x1800a8c31  movss   xmm2, cs:__real@437f0000
0x1800a8c39  divss   xmm3, xmm2
0x1800a8c3d  movzx   ecx, ax
0x1800a8c40  shr     cx, 8
0x1800a8c44  movzx   ecx, cx
0x1800a8c47  movd    xmm1, ecx
0x1800a8c4b  cvtdq2ps xmm1, xmm1
0x1800a8c4e  divss   xmm1, xmm2
0x1800a8c52  movzx   eax, al
0x1800a8c55  movd    xmm0, eax
0x1800a8c59  cvtdq2ps xmm0, xmm0
0x1800a8c5c  divss   xmm0, xmm2
0x1800a8c60  movss   [rbp+var_20], xmm0
0x1800a8c65  movss   [rbp+var_1C], xmm1
0x1800a8c6a  movss   [rbp+var_18], xmm3
0x1800a8c6f  mov     [rbp+var_14], 3F800000h
0x1800a8c76  mov     rax, [r15]
0x1800a8c79  mov     rcx, r15
0x1800a8c7c  mov     rax, [rax+18h]
0x1800a8c80  call    cs:__guard_dispatch_icall_fptr
0x1800a8c86  mov     r8, rax
0x1800a8c89  mov     rcx, [rax]
0x1800a8c8c  mov     rax, [rcx+1C8h]
0x1800a8c93  lea     rdx, [rbp+var_28]
0x1800a8c97  mov     rcx, r8
0x1800a8c9a  call    cs:__guard_dispatch_icall_fptr
0x1800a8ca0  mov     rcx, [rax]
0x1800a8ca3  test    rcx, rcx
0x1800a8ca6  jz      short loc_1800A8CB2
0x1800a8ca8  mov     [rax], rsi
0x1800a8cab  mov     rdi, rcx
0x1800a8cae  mov     [rbp+var_30], rcx
0x1800a8cb2  mov     rcx, [rbp+var_28]
0x1800a8cb6  test    rcx, rcx
0x1800a8cb9  jz      short loc_1800A8CC8
0x1800a8cbb  mov     rax, [rcx]
0x1800a8cbe  mov     rax, [rax+8]
0x1800a8cc2  call    cs:__guard_dispatch_icall_fptr
0x1800a8cc8  mov     rax, [r15]
0x1800a8ccb  mov     rcx, r15
0x1800a8cce  mov     rax, [rax+170h]
0x1800a8cd5  call    cs:__guard_dispatch_icall_fptr
0x1800a8cdb  mov     r9, rax
0x1800a8cde  mov     rcx, [rax]
0x1800a8ce1  mov     rax, [rcx+60h]
0x1800a8ce5  lea     r8, [rbp+var_20]
0x1800a8ce9  mov     rdx, rdi
0x1800a8cec  mov     rcx, r9
0x1800a8cef  call    cs:__guard_dispatch_icall_fptr
0x1800a8cf5  mov     [rbp+arg_0], rsi
0x1800a8cf9  lea     rax, [rbp+arg_0]
0x1800a8cfd  mov     [rsp+80h+var_38], rax
0x1800a8d02  mov     [rsp+80h+var_40], 1
0x1800a8d07  lea     rax, aXNone; "x-none"
0x1800a8d0e  mov     [rsp+80h+var_48], rax
0x1800a8d13  movss   [rsp+80h+var_50], xmm6
0x1800a8d19  mov     dword ptr [rsp+80h+var_58], 5
0x1800a8d21  mov     dword ptr [rsp+80h+var_60], esi
0x1800a8d25  mov     r9d, 190h
0x1800a8d2b  xor     r8d, r8d
0x1800a8d2e  mov     rdx, cs:qword_18052E510
0x1800a8d35  mov     rcx, rbx
0x1800a8d38  call    cs:__imp_?MsoCreateTextFormat@DWriteAssistant@Mso@@YAJAEAUIDWriteFactory@@PEB_WPEAUIDWriteFontCollection@@W4DWRITE_FONT_WEIGHT@@W4DWRITE_FONT_STYLE@@W4DWRITE_FONT_STRETCH@@M1_NPEAPEAUIDWriteTextFormat@@@Z; Mso::DWriteAssistant::MsoCreateTextFormat(IDWriteFactory &,wchar_t const *,IDWriteFontCollection *,DWRITE_FONT_WEIGHT,DWRITE_FONT_STYLE,DWRITE_FONT_STRETCH,float,wchar_t const *,bool,IDWriteTextFormat * *)
0x1800a8d3e  test    eax, eax
0x1800a8d40  js      loc_1800A8E59
0x1800a8d46  mov     rbx, [rbp+arg_0]
0x1800a8d4a  mov     rax, [rbx]
0x1800a8d4d  mov     rsi, [rax+18h]
0x1800a8d51  call    cs:__imp_MsoGetUILcid
0x1800a8d57  mov     ecx, eax
0x1800a8d59  call    cs:__imp_MsoFLidBiDi
0x1800a8d5f  xor     edx, edx
0x1800a8d61  test    eax, eax
0x1800a8d63  setnz   dl
0x1800a8d66  mov     rcx, rbx
0x1800a8d69  mov     rax, rsi
0x1800a8d6c  call    cs:__guard_dispatch_icall_fptr
0x1800a8d72  xor     ebx, ebx
0x1800a8d74  test    eax, eax
0x1800a8d76  js      loc_1800A8E66
0x1800a8d7c  mov     rcx, [rbp+arg_0]
0x1800a8d80  mov     rax, [rcx]
0x1800a8d83  xor     edx, edx
0x1800a8d85  mov     rax, [rax+20h]
0x1800a8d89  call    cs:__guard_dispatch_icall_fptr
0x1800a8d8f  test    eax, eax
0x1800a8d91  js      loc_1800A8E73
0x1800a8d97  mov     rax, [r15]
0x1800a8d9a  inc     r14
0x1800a8d9d  cmp     [r12+r14*2], bx
0x1800a8da2  jnz     short loc_1800A8D9A
0x1800a8da4  mov     dword ptr [rsp+80h+var_48], ebx
0x1800a8da8  mov     [rsp+80h+var_50], ebx
0x1800a8dac  mov     [rsp+80h+var_58], rdi
0x1800a8db1  mov     [rsp+80h+var_60], r13
0x1800a8db6  mov     r9, [rbp+arg_0]
0x1800a8dba  mov     r8d, r14d
0x1800a8dbd  mov     rdx, r12
0x1800a8dc0  mov     rcx, r15
0x1800a8dc3  mov     rax, [rax+120h]
0x1800a8dca  call    cs:__guard_dispatch_icall_fptr
0x1800a8dd0  nop
0x1800a8dd1  mov     rcx, [rbp+arg_0]
0x1800a8dd5  test    rcx, rcx
0x1800a8dd8  jz      short loc_1800A8DE8
0x1800a8dda  mov     rax, [rcx]
0x1800a8ddd  mov     rax, [rax+10h]
0x1800a8de1  call    cs:__guard_dispatch_icall_fptr
0x1800a8de7  nop
0x1800a8de8  test    rdi, rdi
0x1800a8deb  jz      short loc_1800A8DFD
0x1800a8ded  mov     rax, [rdi]
0x1800a8df0  mov     rcx, rdi
0x1800a8df3  mov     rax, [rax+8]
0x1800a8df7  call    cs:__guard_dispatch_icall_fptr
0x1800a8dfd  lea     r11, [rsp+80h+var_s0]
0x1800a8e05  mov     rbx, [r11+38h]
0x1800a8e09  mov     rsi, [r11+40h]
0x1800a8e0d  mov     rdi, [r11+48h]
0x1800a8e11  movaps  xmm6, [rsp+80h+var_10]
0x1800a8e16  mov     rsp, r11
0x1800a8e19  pop     r15
0x1800a8e1b  pop     r14
0x1800a8e1d  pop     r13
0x1800a8e1f  pop     r12
0x1800a8e21  pop     rbp
0x1800a8e22  retn
0x1800a8e23  lea     rcx, dword_18052E508
0x1800a8e2a  call    _Init_thread_header
0x1800a8e2f  cmp     cs:dword_18052E508, r14d
0x1800a8e36  jnz     loc_1800A8C00
0x1800a8e3c  call    ?GetUIFontName@Arc2DTech@GEL@@CAPEB_WXZ; GEL::Arc2DTech::GetUIFontName(void)
0x1800a8e41  mov     cs:qword_18052E510, rax
0x1800a8e48  lea     rcx, dword_18052E508
0x1800a8e4f  call    _Init_thread_footer
0x1800a8e54  jmp     loc_1800A8C00
0x1800a8e59  mov     edx, 121C3CCh; unsigned int
0x1800a8e5e  mov     ecx, eax; int
0x1800a8e60  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1800a8e65  int     3; Trap to Debugger
0x1800a8e66  mov     edx, 121C3CDh; unsigned int
0x1800a8e6b  mov     ecx, eax; int
0x1800a8e6d  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1800a8e72  int     3; Trap to Debugger
0x1800a8e73  mov     edx, 121C3CEh; unsigned int
0x1800a8e78  mov     ecx, eax; int
0x1800a8e7a  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1800a8e7f  int     3; Trap to Debugger
```
