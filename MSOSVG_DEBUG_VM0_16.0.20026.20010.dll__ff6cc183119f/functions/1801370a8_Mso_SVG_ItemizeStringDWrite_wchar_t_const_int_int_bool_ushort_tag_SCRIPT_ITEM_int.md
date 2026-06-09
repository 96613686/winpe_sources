# Mso::SVG::ItemizeStringDWrite(wchar_t const *,int,int,bool,ushort,tag_SCRIPT_ITEM *,int *)

- ea: `0x1801370a8`
- end: `0x180137452`
- name: `?ItemizeStringDWrite@SVG@Mso@@YAJPEB_WHH_NGPEAUtag_SCRIPT_ITEM@@PEAH@Z`
- size: `938`
- prototype: `__int64 __fastcall(Mso::SVG *__hidden this, const wchar_t *, int, int, bool, unsigned __int16, struct tag_SCRIPT_ITEM *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180135a78`

## callees

- `0x180008a80`
- `0x180136ac0`
- `0x1801370a8`
- `0x1801378b8`
- `0x18013d650`
- `0x18013f760`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x1801370fe`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x180137118`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x1801370fe`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x180137118`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1801373e2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1801373e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Mso::SVG::ItemizeStringDWrite(
        Mso::SVG *this,
        const wchar_t *a2,
        int a3,
        unsigned __int8 a4,
        bool a5,
        __int64 a6,
        struct tag_SCRIPT_ITEM *a7)
{
  unsigned __int16 v7; // r15
  int v9; // esi
  __int64 Instance; // rax
  int v13; // r12d
  __int64 v14; // r14
  int v15; // ebx
  __int64 v16; // rcx
  int v18; // r9d
  int v19; // r11d
  __int64 v20; // r8
  unsigned __int64 v21; // r10
  __int64 v22; // rbx
  __int16 v23; // cx
  __int16 v24; // cx
  __int16 v25; // dx
  __int16 v26; // r14
  __int16 v27; // cx
  __int16 v28; // dx
  int v29; // r14d
  unsigned int v30; // eax
  unsigned int v31; // ebx
  __int64 v32; // rcx
  __int64 v33; // rcx
  _BYTE v34[24]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v35[208]; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v36; // [rsp+130h] [rbp+28h]
  __int64 v37; // [rsp+140h] [rbp+38h]
  _BYTE v38[32]; // [rsp+148h] [rbp+40h] BYREF
  _QWORD v39[4]; // [rsp+168h] [rbp+60h] BYREF

  v7 = a4;
  v9 = (int)a2;
  Instance = Mso::DWriteAssistant::ResourceManager::GetInstance();
  v13 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(Instance + 104) + 24LL))(*(_QWORD *)(Instance + 104));
  v14 = *(_QWORD *)(Mso::DWriteAssistant::ResourceManager::GetInstance() + 72);
  Mso::SVG::CTextAnalyzerHelper::CTextAnalyzerHelper(v34, this, (unsigned int)v9, v7);
  v15 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD, _BYTE *))(*(_QWORD *)v14 + 24LL))(
          v14,
          v34,
          0,
          (unsigned int)v9,
          v35);
  if ( v15 < 0 )
  {
    std::vector<Mso::SVG::CTextAnalysisInfo>::~vector<Mso::SVG::CTextAnalysisInfo>(v39);
    std::vector<char>::~vector<char>(v38);
    v16 = v37;
    if ( !v37 )
      return (unsigned int)v15;
    v37 = 0;
LABEL_4:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    return (unsigned int)v15;
  }
  if ( (_BYTE)v7
    && (v15 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD, _BYTE *))(*(_QWORD *)v14 + 32LL))(
                v14,
                v34,
                0,
                (unsigned int)v9,
                v35),
        v15 < 0)
    || v13 != 2
    && (v15 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD, _BYTE *))(*(_QWORD *)v14 + 40LL))(
                v14,
                v34,
                0,
                (unsigned int)v9,
                v35),
        v15 < 0) )
  {
    std::vector<Mso::SVG::CTextAnalysisInfo>::~vector<Mso::SVG::CTextAnalysisInfo>(v39);
    std::vector<char>::~vector<char>(v38);
    v16 = v37;
    if ( !v37 )
      return (unsigned int)v15;
    v37 = 0;
    goto LABEL_4;
  }
  v18 = 0;
  v19 = 0;
  if ( v9 <= 0 )
  {
LABEL_31:
    if ( v19 <= a3 )
      goto LABEL_37;
  }
  else
  {
    v20 = v39[0];
    while ( v19 <= a3 )
    {
      v21 = (v39[1] - v20) >> 4;
      if ( (unsigned int)v18 >= v21 )
LABEL_36:
        _invoke_watson(0, 0, 0, 0, 0);
      v22 = 16LL * (unsigned int)v18;
      *(_DWORD *)a6 = v18;
      *(_WORD *)(a6 + 6) = 0;
      v23 = 0;
      if ( *(_DWORD *)(v22 + v20 + 4) == 1 )
        v23 = 0x8000;
      v24 = *(_WORD *)(a6 + 4) & 0x7FFF | v23;
      *(_WORD *)(a6 + 4) = v24;
      v25 = v24 ^ (*(_WORD *)(v22 + v20) ^ v24) & 0x3FF;
      *(_WORD *)(a6 + 4) = v25;
      v26 = 0;
      if ( *(_DWORD *)(v22 + v20 + 12) != 2 )
      {
        *(_WORD *)(a6 + 6) = 256;
        v26 = 256;
      }
      v27 = v25 & 0xFBFF | ((*(_BYTE *)(v22 + v20 + 8) & 1) << 10);
      *(_WORD *)(a6 + 4) = v27;
      v28 = v27 & 0xF7FF | ((*(_BYTE *)(v22 + v20 + 8) & 1) << 11);
      *(_WORD *)(a6 + 4) = v28;
      *(_WORD *)(a6 + 6) = v26 | *(_BYTE *)(v22 + v20 + 8) & 0x1F;
      *(_WORD *)(a6 + 4) = v28 & 0x8FFF;
      v29 = 1;
      v30 = v18 + 1;
      if ( v18 + 1 < v36 )
      {
        v31 = v18;
        do
        {
          if ( v31 != v30 )
          {
            if ( v30 >= v21 || v31 >= v21 )
              goto LABEL_36;
            if ( *(_DWORD *)(v20 + 16LL * v31 + 4) != *(_DWORD *)(v20 + 16LL * v30 + 4)
              || *(_WORD *)(v20 + 16LL * v31) != *(_WORD *)(v20 + 16LL * v30)
              || *(_BYTE *)(v20 + 16LL * v31 + 8) != *(_BYTE *)(v20 + 16LL * v30 + 8)
              || *(_DWORD *)(v20 + 16LL * v31 + 12) != *(_DWORD *)(v20 + 16LL * v30 + 12) )
            {
              break;
            }
          }
          ++v29;
          v30 = ++v31 + 1;
        }
        while ( v31 + 1 < v36 );
      }
      v18 += v29;
      ++v19;
      a6 += 8;
      if ( v18 >= v9 )
        goto LABEL_31;
    }
  }
  if ( v18 < v9 )
  {
    std::vector<Mso::SVG::CTextAnalysisInfo>::~vector<Mso::SVG::CTextAnalysisInfo>(v39);
    std::vector<char>::~vector<char>(v38);
    v32 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    return 2147942414LL;
  }
LABEL_37:
  *(_DWORD *)a6 = v18;
  a7->iCharPos = v19;
  std::vector<Mso::SVG::CTextAnalysisInfo>::~vector<Mso::SVG::CTextAnalysisInfo>(v39);
  std::vector<char>::~vector<char>(v38);
  v33 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  return 0;
}

```

## disassembly

```asm
0x1801370a8  mov     rax, rsp
0x1801370ab  mov     [rax+8], rbx
0x1801370af  mov     [rax+18h], rsi
0x1801370b3  mov     [rax+20h], rdi
0x1801370b7  push    rbp
0x1801370b8  push    r12
0x1801370ba  push    r13
0x1801370bc  push    r14
0x1801370be  push    r15
0x1801370c0  lea     rbp, [rax-0B8h]
0x1801370c7  sub     rsp, 190h
0x1801370ce  mov     rax, cs:__security_cookie
0x1801370d5  xor     rax, rsp
0x1801370d8  mov     [rbp+0B0h+var_30], rax
0x1801370df  movzx   r15d, r9b
0x1801370e3  mov     r13d, r8d
0x1801370e6  mov     esi, edx
0x1801370e8  mov     rbx, rcx
0x1801370eb  mov     rdi, [rbp+0B0h+arg_28]
0x1801370f2  mov     rax, [rbp+0B0h+arg_30]
0x1801370f9  mov     [rsp+1B0h+var_180], rax
0x1801370fe  call    cs:__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ; Mso::DWriteAssistant::ResourceManager::GetInstance(void)
0x180137104  mov     rcx, [rax+68h]
0x180137108  mov     rax, [rcx]
0x18013710b  mov     rax, [rax+18h]
0x18013710f  call    cs:__guard_dispatch_icall_fptr
0x180137115  mov     r12d, eax
0x180137118  call    cs:__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ; Mso::DWriteAssistant::ResourceManager::GetInstance(void)
0x18013711e  mov     r14, [rax+48h]
0x180137122  movzx   r9d, r15w
0x180137126  mov     dword ptr [rsp+1B0h+var_188], r12d
0x18013712b  mov     r8d, esi
0x18013712e  mov     rdx, rbx
0x180137131  lea     rcx, [rsp+1B0h+var_170]
0x180137136  call    ??0CTextAnalyzerHelper@SVG@Mso@@QEAA@PEB_WHGGW4DWRITE_NUMBER_SUBSTITUTION_METHOD@@@Z; Mso::SVG::CTextAnalyzerHelper::CTextAnalyzerHelper(wchar_t const *,int,ushort,ushort,DWRITE_NUMBER_SUBSTITUTION_METHOD)
0x18013713b  mov     rcx, [r14]
0x18013713e  mov     rax, [rcx+18h]
0x180137142  lea     rcx, [rsp+1B0h+var_158]
0x180137147  mov     [rsp+1B0h+Reserved], rcx
0x18013714c  mov     r9d, esi
0x18013714f  xor     r8d, r8d
0x180137152  lea     rdx, [rsp+1B0h+var_170]
0x180137157  mov     rcx, r14
0x18013715a  call    cs:__guard_dispatch_icall_fptr
0x180137160  mov     ebx, eax
0x180137162  test    eax, eax
0x180137164  jns     short loc_18013719D
0x180137166  lea     rcx, [rbp+0B0h+var_50]
0x18013716a  call    ??1?$vector@UCTextAnalysisInfo@SVG@Mso@@V?$allocator@UCTextAnalysisInfo@SVG@Mso@@@std@@@std@@QEAA@XZ; std::vector<Mso::SVG::CTextAnalysisInfo>::~vector<Mso::SVG::CTextAnalysisInfo>(void)
0x18013716f  lea     rcx, [rbp+0B0h+var_70]
0x180137173  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180137178  mov     rcx, [rbp+0B0h+var_78]
0x18013717c  test    rcx, rcx
0x18013717f  jz      short loc_180137196
0x180137181  mov     [rbp+0B0h+var_78], 0
0x180137189  mov     rdx, [rcx]
0x18013718c  mov     rax, [rdx+10h]
0x180137190  call    cs:__guard_dispatch_icall_fptr
0x180137196  mov     eax, ebx
0x180137198  jmp     loc_180137422
0x18013719d  test    r15b, r15b
0x1801371a0  jz      short loc_1801371F1
0x1801371a2  mov     rax, [r14]
0x1801371a5  lea     rcx, [rsp+1B0h+var_158]
0x1801371aa  mov     [rsp+1B0h+Reserved], rcx
0x1801371af  mov     r9d, esi
0x1801371b2  xor     r8d, r8d
0x1801371b5  lea     rdx, [rsp+1B0h+var_170]
0x1801371ba  mov     rcx, r14
0x1801371bd  mov     rax, [rax+20h]
0x1801371c1  call    cs:__guard_dispatch_icall_fptr
0x1801371c7  mov     ebx, eax
0x1801371c9  xor     r15d, r15d
0x1801371cc  test    eax, eax
0x1801371ce  jns     short loc_1801371F4
0x1801371d0  lea     rcx, [rbp+0B0h+var_50]
0x1801371d4  call    ??1?$vector@UCTextAnalysisInfo@SVG@Mso@@V?$allocator@UCTextAnalysisInfo@SVG@Mso@@@std@@@std@@QEAA@XZ; std::vector<Mso::SVG::CTextAnalysisInfo>::~vector<Mso::SVG::CTextAnalysisInfo>(void)
0x1801371d9  lea     rcx, [rbp+0B0h+var_70]
0x1801371dd  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1801371e2  mov     rcx, [rbp+0B0h+var_78]
0x1801371e6  test    rcx, rcx
0x1801371e9  jz      short loc_180137196
0x1801371eb  mov     [rbp+0B0h+var_78], r15
0x1801371ef  jmp     short loc_180137189
0x1801371f1  xor     r15d, r15d
0x1801371f4  cmp     r12d, 2
0x1801371f8  jz      short loc_180137225
0x1801371fa  mov     rax, [r14]
0x1801371fd  lea     rcx, [rsp+1B0h+var_158]
0x180137202  mov     [rsp+1B0h+Reserved], rcx
0x180137207  mov     r9d, esi
0x18013720a  xor     r8d, r8d
0x18013720d  lea     rdx, [rsp+1B0h+var_170]
0x180137212  mov     rcx, r14
0x180137215  mov     rax, [rax+28h]
0x180137219  call    cs:__guard_dispatch_icall_fptr
0x18013721f  mov     ebx, eax
0x180137221  test    eax, eax
0x180137223  js      short loc_1801371D0
0x180137225  mov     r9d, r15d
0x180137228  mov     r11d, r15d
0x18013722b  test    esi, esi
0x18013722d  jle     loc_180137396
0x180137233  mov     r12d, 1
0x180137239  mov     r8, [rbp+0B0h+var_50]
0x18013723d  cmp     r11d, r13d
0x180137240  jg      loc_18013739B
0x180137246  mov     r10, [rbp+0B0h+var_48]
0x18013724a  sub     r10, r8
0x18013724d  sar     r10, 4
0x180137251  mov     ebx, r9d
0x180137254  cmp     rbx, r10
0x180137257  jnb     loc_1801373D3
0x18013725d  shl     rbx, 4
0x180137261  mov     [rdi], r9d
0x180137264  mov     [rdi+6], r15w
0x180137269  mov     ecx, r15d
0x18013726c  mov     eax, 8000h
0x180137271  cmp     [rbx+r8+4], r12d
0x180137276  cmovz   cx, ax
0x18013727a  movzx   eax, word ptr [rdi+4]
0x18013727e  mov     edx, 7FFFh
0x180137283  and     ax, dx
0x180137286  or      cx, ax
0x180137289  mov     [rdi+4], cx
0x18013728d  movzx   edx, cx
0x180137290  xor     dx, [rbx+r8]
0x180137295  mov     eax, 3FFh
0x18013729a  and     dx, ax
0x18013729d  xor     dx, cx
0x1801372a0  mov     [rdi+4], dx
0x1801372a4  movzx   r14d, r15w
0x1801372a8  cmp     dword ptr [rbx+r8+0Ch], 2
0x1801372ae  jz      short loc_1801372BC
0x1801372b0  mov     eax, 100h
0x1801372b5  mov     [rdi+6], ax
0x1801372b9  mov     r14d, eax
0x1801372bc  mov     al, [rbx+r8+8]
0x1801372c1  and     al, r12b
0x1801372c4  movzx   ecx, al
0x1801372c7  shl     cx, 0Ah
0x1801372cb  mov     eax, 0FBFFh
0x1801372d0  and     dx, ax
0x1801372d3  or      cx, dx
0x1801372d6  mov     [rdi+4], cx
0x1801372da  mov     al, [rbx+r8+8]
0x1801372df  and     al, r12b
0x1801372e2  movzx   edx, al
0x1801372e5  shl     dx, 0Bh
0x1801372e9  mov     eax, 0F7FFh
0x1801372ee  and     cx, ax
0x1801372f1  or      dx, cx
0x1801372f4  mov     [rdi+4], dx
0x1801372f8  mov     al, [rbx+r8+8]
0x1801372fd  and     al, 1Fh
0x1801372ff  movzx   ecx, al
0x180137302  or      cx, r14w
0x180137306  mov     [rdi+6], cx
0x18013730a  mov     eax, 8FFFh
0x18013730f  and     dx, ax
0x180137312  mov     [rdi+4], dx
0x180137316  mov     r14d, r12d
0x180137319  lea     eax, [r9+1]
0x18013731d  cmp     eax, [rbp+0B0h+var_88]
0x180137320  jnb     short loc_180137383
0x180137322  mov     ebx, r9d
0x180137325  cmp     ebx, eax
0x180137327  jz      short loc_180137375
0x180137329  mov     edx, eax
0x18013732b  cmp     rdx, r10
0x18013732e  jnb     loc_1801373D3
0x180137334  mov     ecx, ebx
0x180137336  cmp     rcx, r10
0x180137339  jnb     loc_1801373D3
0x18013733f  add     rdx, rdx
0x180137342  add     rcx, rcx
0x180137345  mov     eax, [r8+rdx*8+4]
0x18013734a  cmp     [r8+rcx*8+4], eax
0x18013734f  jnz     short loc_180137383
0x180137351  movzx   eax, word ptr [r8+rdx*8]
0x180137356  cmp     [r8+rcx*8], ax
0x18013735b  jnz     short loc_180137383
0x18013735d  mov     al, [r8+rdx*8+8]
0x180137362  cmp     [r8+rcx*8+8], al
0x180137367  jnz     short loc_180137383
0x180137369  mov     eax, [r8+rdx*8+0Ch]
0x18013736e  cmp     [r8+rcx*8+0Ch], eax
0x180137373  jnz     short loc_180137383
0x180137375  add     r14d, r12d
0x180137378  add     ebx, r12d
0x18013737b  lea     eax, [rbx+1]
0x18013737e  cmp     eax, [rbp+0B0h+var_88]
0x180137381  jb      short loc_180137325
0x180137383  add     r9d, r14d
0x180137386  add     r11d, r12d
0x180137389  add     rdi, 8
0x18013738d  cmp     r9d, esi
0x180137390  jl      loc_18013723D
0x180137396  cmp     r11d, r13d
0x180137399  jle     short loc_1801373E9
0x18013739b  cmp     r9d, esi
0x18013739e  jge     short loc_1801373E9
0x1801373a0  lea     rcx, [rbp+0B0h+var_50]
0x1801373a4  call    ??1?$vector@UCTextAnalysisInfo@SVG@Mso@@V?$allocator@UCTextAnalysisInfo@SVG@Mso@@@std@@@std@@QEAA@XZ; std::vector<Mso::SVG::CTextAnalysisInfo>::~vector<Mso::SVG::CTextAnalysisInfo>(void)
0x1801373a9  lea     rcx, [rbp+0B0h+var_70]
0x1801373ad  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1801373b2  mov     rcx, [rbp+0B0h+var_78]
0x1801373b6  test    rcx, rcx
0x1801373b9  jz      short loc_1801373CC
0x1801373bb  mov     [rbp+0B0h+var_78], r15
0x1801373bf  mov     rax, [rcx]
0x1801373c2  mov     rax, [rax+10h]
0x1801373c6  call    cs:__guard_dispatch_icall_fptr
0x1801373cc  mov     eax, 8007000Eh
0x1801373d1  jmp     short loc_180137422
0x1801373d3  mov     [rsp+1B0h+Reserved], r15; Reserved
0x1801373d8  xor     r9d, r9d; LineNo
0x1801373db  xor     r8d, r8d; FileName
0x1801373de  xor     edx, edx; FunctionName
0x1801373e0  xor     ecx, ecx; Expression
0x1801373e2  call    cs:__imp__invoke_watson
0x1801373e9  mov     [rdi], r9d
0x1801373ec  mov     rax, [rsp+1B0h+var_180]
0x1801373f1  mov     [rax], r11d
0x1801373f4  lea     rcx, [rbp+0B0h+var_50]
0x1801373f8  call    ??1?$vector@UCTextAnalysisInfo@SVG@Mso@@V?$allocator@UCTextAnalysisInfo@SVG@Mso@@@std@@@std@@QEAA@XZ; std::vector<Mso::SVG::CTextAnalysisInfo>::~vector<Mso::SVG::CTextAnalysisInfo>(void)
0x1801373fd  lea     rcx, [rbp+0B0h+var_70]
0x180137401  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180137406  mov     rcx, [rbp+0B0h+var_78]
0x18013740a  test    rcx, rcx
0x18013740d  jz      short loc_180137420
0x18013740f  mov     [rbp+0B0h+var_78], r15
0x180137413  mov     rax, [rcx]
0x180137416  mov     rax, [rax+10h]
0x18013741a  call    cs:__guard_dispatch_icall_fptr
0x180137420  xor     eax, eax
0x180137422  mov     rcx, [rbp+0B0h+var_30]
0x180137429  xor     rcx, rsp; StackCookie
0x18013742c  call    __security_check_cookie
0x180137431  lea     r11, [rsp+1B0h+var_20]
0x180137439  mov     rbx, [r11+30h]
0x18013743d  mov     rsi, [r11+40h]
0x180137441  mov     rdi, [r11+48h]
0x180137445  mov     rsp, r11
0x180137448  pop     r15
0x18013744a  pop     r14
0x18013744c  pop     r13
0x18013744e  pop     r12
0x180137450  pop     rbp
0x180137451  retn
```
