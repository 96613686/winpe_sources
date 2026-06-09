# Microsoft::Windows::Performance::CCvDDCache::AddFailure(ushort const *,ulong)

- ea: `0x180009704`
- end: `0x1800098cf`
- name: `?AddFailure@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGK@Z`
- size: `459`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a30c`

## callees

- `0x180008d5c`
- `0x180009660`
- `0x180009704`
- `0x18000d360`
- `0x18000d48c`
- `0x18000d560`
- `0x180013598`
- `0x1800268f4`
- `0x180026e30`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Performance::CCvDDCache::AddFailure(
        Microsoft::Windows::Performance::CCvDDCache *this,
        const unsigned __int16 *a2,
        int a3)
{
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 *v8; // rdi
  __int64 v9; // rax
  __int64 result; // rax
  __int64 v11; // [rsp+60h] [rbp-158h] BYREF
  int v12; // [rsp+68h] [rbp-150h] BYREF
  __int64 v13; // [rsp+70h] [rbp-148h]
  _BYTE v14[8]; // [rsp+78h] [rbp-140h] BYREF
  void *Block; // [rsp+80h] [rbp-138h]
  __int64 v16; // [rsp+90h] [rbp-128h]
  unsigned __int64 v17; // [rsp+98h] [rbp-120h]
  _BYTE v18[8]; // [rsp+A0h] [rbp-118h] BYREF
  void *v19; // [rsp+A8h] [rbp-110h]
  __int64 v20; // [rsp+B8h] [rbp-100h]
  unsigned __int64 v21; // [rsp+C0h] [rbp-F8h]
  _BYTE v22[176]; // [rsp+D0h] [rbp-E8h] BYREF

  v13 = -2;
  v12 = a3;
  try
  {
    v21 = 7;
    v20 = 0;
    LOWORD(v19) = 0;
    std::wstring::assign(v18, &qword_18002BEF8);
    v17 = 7;
    v16 = 0;
    LOWORD(Block) = 0;
    std::wstring::assign(v14, a2);
    v6 = Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
           (__int64)v22,
           (__int64)v14,
           (__int64)v18,
           0,
           0,
           0,
           0,
           a3,
           0,
           0,
           0,
           0);
    std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(this, v6);
    Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD((Microsoft::Windows::Performance::CCvDDCache::CCvDD *)v22);
    if ( v17 >= 8 )
      operator delete(Block);
    v17 = 7;
    v16 = 0;
    LOWORD(Block) = 0;
    if ( v21 >= 8 )
      operator delete(v19);
    v7 = *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
    v8 = (__int64 *)(v7 + 24);
    if ( *(_QWORD *)(v7 + 48) < 8u )
      v11 = v7 + 24;
    else
      v11 = *v8;
    v9 = std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](
           (char *)this + 24,
           &v12);
    *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
                 v9,
                 &v11) = 0;
    if ( *(_QWORD *)(v7 + 48) < 8u )
      v11 = v7 + 24;
    else
      v11 = *v8;
    *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
                 (char *)this + 48,
                 &v11) = 0;
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180009704  mov     r11, rsp
0x180009707  push    rbx
0x180009708  push    rsi
0x180009709  push    rdi
0x18000970a  push    r14
0x18000970c  push    r15
0x18000970e  sub     rsp, 190h
0x180009715  mov     [rsp+1B8h+var_148], 0FFFFFFFFFFFFFFFEh
0x18000971e  mov     rax, cs:__security_cookie
0x180009725  xor     rax, rsp
0x180009728  mov     [rsp+1B8h+var_38], rax
0x180009730  mov     ebx, r8d
0x180009733  mov     rdi, rdx
0x180009736  mov     rsi, rcx
0x180009739  mov     [rsp+1B8h+var_150], ebx
0x18000973d  mov     r15d, 7
0x180009743  mov     [r11-0F8h], r15
0x18000974a  xor     r14d, r14d
0x18000974d  mov     [r11-100h], r14
0x180009754  mov     [r11-110h], r14w
0x18000975c  lea     rdx, qword_18002BEF8
0x180009763  lea     rcx, [r11-118h]
0x18000976a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000976f  nop
0x180009770  mov     [rsp+1B8h+var_120], r15
0x180009778  mov     [rsp+1B8h+var_128], r14
0x180009780  mov     word ptr [rsp+1B8h+Block], r14w
0x180009789  mov     rdx, rdi
0x18000978c  lea     rcx, [rsp+1B8h+var_140]
0x180009791  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180009796  nop
0x180009797  mov     [rsp+1B8h+var_160], r14b
0x18000979c  mov     [rsp+1B8h+var_168], r14
0x1800097a1  mov     [rsp+1B8h+var_170], r14d
0x1800097a6  mov     [rsp+1B8h+var_178], r14d
0x1800097ab  mov     [rsp+1B8h+var_180], ebx
0x1800097af  mov     [rsp+1B8h+var_188], r14
0x1800097b4  mov     [rsp+1B8h+var_190], r14
0x1800097b9  mov     [rsp+1B8h+var_198], r14
0x1800097be  xor     r9d, r9d
0x1800097c1  lea     r8, [rsp+1B8h+var_118]
0x1800097c9  lea     rdx, [rsp+1B8h+var_140]
0x1800097ce  lea     rcx, [rsp+1B8h+var_E8]
0x1800097d6  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::wstring const &,std::wstring const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)
0x1800097db  nop
0x1800097dc  mov     rdx, rax
0x1800097df  mov     rcx, rsi
0x1800097e2  call    ?push_back@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAXAEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(Microsoft::Windows::Performance::CCvDDCache::CCvDD const &)
0x1800097e7  nop
0x1800097e8  lea     rcx, [rsp+1B8h+var_E8]; this
0x1800097f0  call    ??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)
0x1800097f5  nop
0x1800097f6  cmp     [rsp+1B8h+var_120], 8
0x1800097ff  jb      short loc_18000980E
0x180009801  mov     rcx, [rsp+1B8h+Block]; Block
0x180009809  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000980e  mov     [rsp+1B8h+var_120], r15
0x180009816  mov     [rsp+1B8h+var_128], r14
0x18000981e  mov     word ptr [rsp+1B8h+Block], r14w
0x180009827  cmp     [rsp+1B8h+var_F8], 8
0x180009830  jb      short loc_18000983F
0x180009832  mov     rcx, [rsp+1B8h+var_110]; Block
0x18000983a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000983f  mov     rbx, [rsi+8]
0x180009843  mov     rbx, [rbx+8]
0x180009847  lea     rdi, [rbx+18h]
0x18000984b  cmp     qword ptr [rbx+30h], 8
0x180009850  jb      short loc_18000985C
0x180009852  mov     rax, [rdi]
0x180009855  mov     [rsp+1B8h+var_158], rax
0x18000985a  jmp     short loc_180009861
0x18000985c  mov     [rsp+1B8h+var_158], rdi
0x180009861  lea     rcx, [rsi+18h]
0x180009865  lea     rdx, [rsp+1B8h+var_150]
0x18000986a  call    ??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](ulong const &)
0x18000986f  lea     rdx, [rsp+1B8h+var_158]
0x180009874  mov     rcx, rax
0x180009877  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@AEBQEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * const &)
0x18000987c  mov     [rax], r14
0x18000987f  cmp     qword ptr [rbx+30h], 8
0x180009884  jb      short loc_180009890
0x180009886  mov     rax, [rdi]
0x180009889  mov     [rsp+1B8h+var_158], rax
0x18000988e  jmp     short loc_180009895
0x180009890  mov     [rsp+1B8h+var_158], rdi
0x180009895  lea     rcx, [rsi+30h]
0x180009899  lea     rdx, [rsp+1B8h+var_158]
0x18000989e  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@AEBQEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * const &)
0x1800098a3  mov     [rax], r14
0x1800098a6  xor     eax, eax
0x1800098a8  jmp     short loc_1800098AF
0x1800098aa  mov     eax, 8007000Eh
0x1800098af  mov     rcx, [rsp+1B8h+var_38]
0x1800098b7  xor     rcx, rsp; StackCookie
0x1800098ba  call    __security_check_cookie
0x1800098bf  add     rsp, 190h
0x1800098c6  pop     r15
0x1800098c8  pop     r14
0x1800098ca  pop     rdi
0x1800098cb  pop     rsi
0x1800098cc  pop     rbx
0x1800098cd  retn
```
