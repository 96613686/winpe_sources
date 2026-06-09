# Mso::SVG::ItemizeStringDWrite(wchar_t const *,int,int,bool,ushort,tag_SCRIPT_ITEM *,int *)

- ea: `0x1801370e8`
- end: `0x180137492`
- name: `?ItemizeStringDWrite@SVG@Mso@@YAJPEB_WHH_NGPEAUtag_SCRIPT_ITEM@@PEAH@Z`
- size: `938`
- prototype: `__int64 __fastcall(Mso::SVG *__hidden this, const wchar_t *, int, int, bool, unsigned __int16, struct tag_SCRIPT_ITEM *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180135ab8`

## callees

- `0x180008a80`
- `0x180136b00`
- `0x1801370e8`
- `0x1801378f8`
- `0x18013d700`
- `0x18013f810`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x18013713e`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x180137158`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x18013713e`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x180137158`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180137422`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180137422`

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
0x1801370e8  mov     rax, rsp
0x1801370eb  mov     [rax+8], rbx
0x1801370ef  mov     [rax+18h], rsi
0x1801370f3  mov     [rax+20h], rdi
0x1801370f7  push    rbp
0x1801370f8  push    r12
0x1801370fa  push    r13
0x1801370fc  push    r14
0x1801370fe  push    r15
0x180137100  lea     rbp, [rax-0B8h]
0x180137107  sub     rsp, 190h
0x18013710e  mov     rax, cs:__security_cookie
0x180137115  xor     rax, rsp
0x180137118  mov     [rbp+0B0h+var_30], rax
0x18013711f  movzx   r15d, r9b
0x180137123  mov     r13d, r8d
0x180137126  mov     esi, edx
0x180137128  mov     rbx, rcx
0x18013712b  mov     rdi, [rbp+0B0h+arg_28]
0x180137132  mov     rax, [rbp+0B0h+arg_30]
0x180137139  mov     [rsp+1B0h+var_180], rax
0x18013713e  call    cs:__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ; Mso::DWriteAssistant::ResourceManager::GetInstance(void)
0x180137144  mov     rcx, [rax+68h]
0x180137148  mov     rax, [rcx]
0x18013714b  mov     rax, [rax+18h]
0x18013714f  call    cs:__guard_dispatch_icall_fptr
0x180137155  mov     r12d, eax
0x180137158  call    cs:__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ; Mso::DWriteAssistant::ResourceManager::GetInstance(void)
0x18013715e  mov     r14, [rax+48h]
0x180137162  movzx   r9d, r15w
0x180137166  mov     dword ptr [rsp+1B0h+var_188], r12d
0x18013716b  mov     r8d, esi
0x18013716e  mov     rdx, rbx
0x180137171  lea     rcx, [rsp+1B0h+var_170]
0x180137176  call    ??0CTextAnalyzerHelper@SVG@Mso@@QEAA@PEB_WHGGW4DWRITE_NUMBER_SUBSTITUTION_METHOD@@@Z; Mso::SVG::CTextAnalyzerHelper::CTextAnalyzerHelper(wchar_t const *,int,ushort,ushort,DWRITE_NUMBER_SUBSTITUTION_METHOD)
0x18013717b  mov     rcx, [r14]
0x18013717e  mov     rax, [rcx+18h]
0x180137182  lea     rcx, [rsp+1B0h+var_158]
0x180137187  mov     [rsp+1B0h+Reserved], rcx
0x18013718c  mov     r9d, esi
0x18013718f  xor     r8d, r8d
0x180137192  lea     rdx, [rsp+1B0h+var_170]
0x180137197  mov     rcx, r14
0x18013719a  call    cs:__guard_dispatch_icall_fptr
0x1801371a0  mov     ebx, eax
0x1801371a2  test    eax, eax
0x1801371a4  jns     short loc_1801371DD
0x1801371a6  lea     rcx, [rbp+0B0h+var_50]
0x1801371aa  call    ??1?$vector@UCTextAnalysisInfo@SVG@Mso@@V?$allocator@UCTextAnalysisInfo@SVG@Mso@@@std@@@std@@QEAA@XZ; std::vector<Mso::SVG::CTextAnalysisInfo>::~vector<Mso::SVG::CTextAnalysisInfo>(void)
0x1801371af  lea     rcx, [rbp+0B0h+var_70]
0x1801371b3  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1801371b8  mov     rcx, [rbp+0B0h+var_78]
0x1801371bc  test    rcx, rcx
0x1801371bf  jz      short loc_1801371D6
0x1801371c1  mov     [rbp+0B0h+var_78], 0
0x1801371c9  mov     rdx, [rcx]
0x1801371cc  mov     rax, [rdx+10h]
0x1801371d0  call    cs:__guard_dispatch_icall_fptr
0x1801371d6  mov     eax, ebx
0x1801371d8  jmp     loc_180137462
0x1801371dd  test    r15b, r15b
0x1801371e0  jz      short loc_180137231
0x1801371e2  mov     rax, [r14]
0x1801371e5  lea     rcx, [rsp+1B0h+var_158]
0x1801371ea  mov     [rsp+1B0h+Reserved], rcx
0x1801371ef  mov     r9d, esi
0x1801371f2  xor     r8d, r8d
0x1801371f5  lea     rdx, [rsp+1B0h+var_170]
0x1801371fa  mov     rcx, r14
0x1801371fd  mov     rax, [rax+20h]
0x180137201  call    cs:__guard_dispatch_icall_fptr
0x180137207  mov     ebx, eax
0x180137209  xor     r15d, r15d
0x18013720c  test    eax, eax
0x18013720e  jns     short loc_180137234
0x180137210  lea     rcx, [rbp+0B0h+var_50]
0x180137214  call    ??1?$vector@UCTextAnalysisInfo@SVG@Mso@@V?$allocator@UCTextAnalysisInfo@SVG@Mso@@@std@@@std@@QEAA@XZ; std::vector<Mso::SVG::CTextAnalysisInfo>::~vector<Mso::SVG::CTextAnalysisInfo>(void)
0x180137219  lea     rcx, [rbp+0B0h+var_70]
0x18013721d  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180137222  mov     rcx, [rbp+0B0h+var_78]
0x180137226  test    rcx, rcx
0x180137229  jz      short loc_1801371D6
0x18013722b  mov     [rbp+0B0h+var_78], r15
0x18013722f  jmp     short loc_1801371C9
0x180137231  xor     r15d, r15d
0x180137234  cmp     r12d, 2
0x180137238  jz      short loc_180137265
0x18013723a  mov     rax, [r14]
0x18013723d  lea     rcx, [rsp+1B0h+var_158]
0x180137242  mov     [rsp+1B0h+Reserved], rcx
0x180137247  mov     r9d, esi
0x18013724a  xor     r8d, r8d
0x18013724d  lea     rdx, [rsp+1B0h+var_170]
0x180137252  mov     rcx, r14
0x180137255  mov     rax, [rax+28h]
0x180137259  call    cs:__guard_dispatch_icall_fptr
0x18013725f  mov     ebx, eax
0x180137261  test    eax, eax
0x180137263  js      short loc_180137210
0x180137265  mov     r9d, r15d
0x180137268  mov     r11d, r15d
0x18013726b  test    esi, esi
0x18013726d  jle     loc_1801373D6
0x180137273  mov     r12d, 1
0x180137279  mov     r8, [rbp+0B0h+var_50]
0x18013727d  cmp     r11d, r13d
0x180137280  jg      loc_1801373DB
0x180137286  mov     r10, [rbp+0B0h+var_48]
0x18013728a  sub     r10, r8
0x18013728d  sar     r10, 4
0x180137291  mov     ebx, r9d
0x180137294  cmp     rbx, r10
0x180137297  jnb     loc_180137413
0x18013729d  shl     rbx, 4
0x1801372a1  mov     [rdi], r9d
0x1801372a4  mov     [rdi+6], r15w
0x1801372a9  mov     ecx, r15d
0x1801372ac  mov     eax, 8000h
0x1801372b1  cmp     [rbx+r8+4], r12d
0x1801372b6  cmovz   cx, ax
0x1801372ba  movzx   eax, word ptr [rdi+4]
0x1801372be  mov     edx, 7FFFh
0x1801372c3  and     ax, dx
0x1801372c6  or      cx, ax
0x1801372c9  mov     [rdi+4], cx
0x1801372cd  movzx   edx, cx
0x1801372d0  xor     dx, [rbx+r8]
0x1801372d5  mov     eax, 3FFh
0x1801372da  and     dx, ax
0x1801372dd  xor     dx, cx
0x1801372e0  mov     [rdi+4], dx
0x1801372e4  movzx   r14d, r15w
0x1801372e8  cmp     dword ptr [rbx+r8+0Ch], 2
0x1801372ee  jz      short loc_1801372FC
0x1801372f0  mov     eax, 100h
0x1801372f5  mov     [rdi+6], ax
0x1801372f9  mov     r14d, eax
0x1801372fc  mov     al, [rbx+r8+8]
0x180137301  and     al, r12b
0x180137304  movzx   ecx, al
0x180137307  shl     cx, 0Ah
0x18013730b  mov     eax, 0FBFFh
0x180137310  and     dx, ax
0x180137313  or      cx, dx
0x180137316  mov     [rdi+4], cx
0x18013731a  mov     al, [rbx+r8+8]
0x18013731f  and     al, r12b
0x180137322  movzx   edx, al
0x180137325  shl     dx, 0Bh
0x180137329  mov     eax, 0F7FFh
0x18013732e  and     cx, ax
0x180137331  or      dx, cx
0x180137334  mov     [rdi+4], dx
0x180137338  mov     al, [rbx+r8+8]
0x18013733d  and     al, 1Fh
0x18013733f  movzx   ecx, al
0x180137342  or      cx, r14w
0x180137346  mov     [rdi+6], cx
0x18013734a  mov     eax, 8FFFh
0x18013734f  and     dx, ax
0x180137352  mov     [rdi+4], dx
0x180137356  mov     r14d, r12d
0x180137359  lea     eax, [r9+1]
0x18013735d  cmp     eax, [rbp+0B0h+var_88]
0x180137360  jnb     short loc_1801373C3
0x180137362  mov     ebx, r9d
0x180137365  cmp     ebx, eax
0x180137367  jz      short loc_1801373B5
0x180137369  mov     edx, eax
0x18013736b  cmp     rdx, r10
0x18013736e  jnb     loc_180137413
0x180137374  mov     ecx, ebx
0x180137376  cmp     rcx, r10
0x180137379  jnb     loc_180137413
0x18013737f  add     rdx, rdx
0x180137382  add     rcx, rcx
0x180137385  mov     eax, [r8+rdx*8+4]
0x18013738a  cmp     [r8+rcx*8+4], eax
0x18013738f  jnz     short loc_1801373C3
0x180137391  movzx   eax, word ptr [r8+rdx*8]
0x180137396  cmp     [r8+rcx*8], ax
0x18013739b  jnz     short loc_1801373C3
0x18013739d  mov     al, [r8+rdx*8+8]
0x1801373a2  cmp     [r8+rcx*8+8], al
0x1801373a7  jnz     short loc_1801373C3
0x1801373a9  mov     eax, [r8+rdx*8+0Ch]
0x1801373ae  cmp     [r8+rcx*8+0Ch], eax
0x1801373b3  jnz     short loc_1801373C3
0x1801373b5  add     r14d, r12d
0x1801373b8  add     ebx, r12d
0x1801373bb  lea     eax, [rbx+1]
0x1801373be  cmp     eax, [rbp+0B0h+var_88]
0x1801373c1  jb      short loc_180137365
0x1801373c3  add     r9d, r14d
0x1801373c6  add     r11d, r12d
0x1801373c9  add     rdi, 8
0x1801373cd  cmp     r9d, esi
0x1801373d0  jl      loc_18013727D
0x1801373d6  cmp     r11d, r13d
0x1801373d9  jle     short loc_180137429
0x1801373db  cmp     r9d, esi
0x1801373de  jge     short loc_180137429
0x1801373e0  lea     rcx, [rbp+0B0h+var_50]
0x1801373e4  call    ??1?$vector@UCTextAnalysisInfo@SVG@Mso@@V?$allocator@UCTextAnalysisInfo@SVG@Mso@@@std@@@std@@QEAA@XZ; std::vector<Mso::SVG::CTextAnalysisInfo>::~vector<Mso::SVG::CTextAnalysisInfo>(void)
0x1801373e9  lea     rcx, [rbp+0B0h+var_70]
0x1801373ed  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1801373f2  mov     rcx, [rbp+0B0h+var_78]
0x1801373f6  test    rcx, rcx
0x1801373f9  jz      short loc_18013740C
0x1801373fb  mov     [rbp+0B0h+var_78], r15
0x1801373ff  mov     rax, [rcx]
0x180137402  mov     rax, [rax+10h]
0x180137406  call    cs:__guard_dispatch_icall_fptr
0x18013740c  mov     eax, 8007000Eh
0x180137411  jmp     short loc_180137462
0x180137413  mov     [rsp+1B0h+Reserved], r15; Reserved
0x180137418  xor     r9d, r9d; LineNo
0x18013741b  xor     r8d, r8d; FileName
0x18013741e  xor     edx, edx; FunctionName
0x180137420  xor     ecx, ecx; Expression
0x180137422  call    cs:__imp__invoke_watson
0x180137429  mov     [rdi], r9d
0x18013742c  mov     rax, [rsp+1B0h+var_180]
0x180137431  mov     [rax], r11d
0x180137434  lea     rcx, [rbp+0B0h+var_50]
0x180137438  call    ??1?$vector@UCTextAnalysisInfo@SVG@Mso@@V?$allocator@UCTextAnalysisInfo@SVG@Mso@@@std@@@std@@QEAA@XZ; std::vector<Mso::SVG::CTextAnalysisInfo>::~vector<Mso::SVG::CTextAnalysisInfo>(void)
0x18013743d  lea     rcx, [rbp+0B0h+var_70]
0x180137441  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180137446  mov     rcx, [rbp+0B0h+var_78]
0x18013744a  test    rcx, rcx
0x18013744d  jz      short loc_180137460
0x18013744f  mov     [rbp+0B0h+var_78], r15
0x180137453  mov     rax, [rcx]
0x180137456  mov     rax, [rax+10h]
0x18013745a  call    cs:__guard_dispatch_icall_fptr
0x180137460  xor     eax, eax
0x180137462  mov     rcx, [rbp+0B0h+var_30]
0x180137469  xor     rcx, rsp; StackCookie
0x18013746c  call    __security_check_cookie
0x180137471  lea     r11, [rsp+1B0h+var_20]
0x180137479  mov     rbx, [r11+30h]
0x18013747d  mov     rsi, [r11+40h]
0x180137481  mov     rdi, [r11+48h]
0x180137485  mov     rsp, r11
0x180137488  pop     r15
0x18013748a  pop     r14
0x18013748c  pop     r13
0x18013748e  pop     r12
0x180137490  pop     rbp
0x180137491  retn
```
