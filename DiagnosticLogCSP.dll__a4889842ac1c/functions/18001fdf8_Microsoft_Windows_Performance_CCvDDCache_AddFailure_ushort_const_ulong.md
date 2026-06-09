# Microsoft::Windows::Performance::CCvDDCache::AddFailure(ushort const *,ulong)

- ea: `0x18001fdf8`
- end: `0x18001ffe5`
- name: `?AddFailure@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGK@Z`
- size: `493`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020204`

## callees

- `0x180001b60`
- `0x180001bc8`
- `0x18000a600`
- `0x18000fb98`
- `0x18001e0d4`
- `0x18001ef84`
- `0x18001f744`
- `0x18001f880`
- `0x18001fdf8`
- `0x180026a08`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CCvDDCache::AddFailure(
        Microsoft::Windows::Performance::CCvDDCache *this,
        const unsigned __int16 *a2,
        int a3)
{
  unsigned __int64 v6; // r8
  __int64 v7; // rdx
  _QWORD *v8; // rbx
  __int64 *v9; // rax
  _QWORD *v10; // rcx
  int v12; // [rsp+60h] [rbp-108h] BYREF
  _QWORD *v13; // [rsp+68h] [rbp-100h] BYREF
  _OWORD v14[2]; // [rsp+70h] [rbp-F8h] BYREF
  _OWORD v15[2]; // [rsp+90h] [rbp-D8h] BYREF
  char *v16[4]; // [rsp+B0h] [rbp-B8h] BYREF
  char *v17; // [rsp+D0h] [rbp-98h] BYREF
  void *v18; // [rsp+F8h] [rbp-70h]
  void *v19; // [rsp+100h] [rbp-68h]
  void *v20; // [rsp+108h] [rbp-60h]
  char *v21; // [rsp+110h] [rbp-58h] BYREF

  v12 = a3;
  memset(v15, 0, sizeof(v15));
  std::wstring::_Construct<1,unsigned short const *>((char **)v15, &String2, 0);
  memset(v14, 0, sizeof(v14));
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  std::wstring::_Construct<1,unsigned short const *>((char **)v14, a2, v6);
  v7 = Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
         (__int64)v16,
         (__int64)v14,
         (__int64)v15,
         0,
         0,
         0,
         0,
         a3,
         0,
         0,
         0,
         0);
  std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(this, v7);
  std::vector<char>::~vector<char>(&v21);
  operator delete(v20);
  v20 = 0;
  operator delete(v19);
  v19 = 0;
  operator delete(v18);
  v18 = 0;
  std::wstring::~wstring(&v17);
  std::wstring::~wstring(v16);
  std::wstring::~wstring((char **)v14);
  std::wstring::~wstring((char **)v15);
  v8 = (_QWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 16LL);
  v9 = (__int64 *)std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](
                    (__int64 *)this + 2,
                    (unsigned int *)&v12);
  if ( v8[3] <= 7u )
    v10 = v8;
  else
    v10 = (_QWORD *)*v8;
  v13 = v10;
  *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
               v9,
               &v13) = 0;
  if ( v8[3] > 7u )
    v8 = (_QWORD *)*v8;
  v13 = v8;
  *(_QWORD *)std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
               (__int64 *)this + 4,
               &v13) = 0;
  return 0;
}

```

## disassembly

```asm
0x18001fdf8  mov     [rsp+arg_18], rbx
0x18001fdfd  push    rsi
0x18001fdfe  push    rdi
0x18001fdff  push    r14
0x18001fe01  sub     rsp, 150h
0x18001fe08  mov     rax, cs:__security_cookie
0x18001fe0f  xor     rax, rsp
0x18001fe12  mov     [rsp+168h+var_28], rax
0x18001fe1a  mov     esi, r8d
0x18001fe1d  mov     rbx, rdx
0x18001fe20  mov     rdi, rcx
0x18001fe23  mov     [rsp+168h+var_108], r8d
0x18001fe28  xorps   xmm0, xmm0
0x18001fe2b  movups  [rsp+168h+var_D8], xmm0
0x18001fe33  xorps   xmm1, xmm1
0x18001fe36  movdqu  [rsp+168h+var_C8], xmm1
0x18001fe3f  xor     r8d, r8d
0x18001fe42  lea     rdx, String2
0x18001fe49  lea     rcx, [rsp+168h+var_D8]
0x18001fe51  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001fe56  nop
0x18001fe57  xorps   xmm0, xmm0
0x18001fe5a  movups  [rsp+168h+var_F8], xmm0
0x18001fe5f  xorps   xmm1, xmm1
0x18001fe62  movdqu  [rsp+168h+var_E8], xmm1
0x18001fe6b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001fe6f  xor     r14d, r14d
0x18001fe72  inc     r8
0x18001fe75  cmp     [rbx+r8*2], r14w
0x18001fe7a  jnz     short loc_18001FE72
0x18001fe7c  mov     rdx, rbx
0x18001fe7f  lea     rcx, [rsp+168h+var_F8]
0x18001fe84  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001fe89  nop
0x18001fe8a  mov     [rsp+168h+var_110], r14b
0x18001fe8f  mov     [rsp+168h+var_118], r14
0x18001fe94  mov     [rsp+168h+var_120], r14d
0x18001fe99  mov     [rsp+168h+var_128], r14d
0x18001fe9e  mov     [rsp+168h+var_130], esi
0x18001fea2  mov     [rsp+168h+var_138], r14
0x18001fea7  mov     [rsp+168h+var_140], r14
0x18001feac  mov     [rsp+168h+var_148], r14
0x18001feb1  xor     r9d, r9d
0x18001feb4  lea     r8, [rsp+168h+var_D8]
0x18001febc  lea     rdx, [rsp+168h+var_F8]
0x18001fec1  lea     rcx, [rsp+168h+var_B8]
0x18001fec9  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::wstring const &,std::wstring const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)
0x18001fece  nop
0x18001fecf  mov     rdx, rax
0x18001fed2  mov     rcx, rdi
0x18001fed5  call    ?push_back@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAX$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)
0x18001feda  nop
0x18001fedb  lea     rcx, [rsp+168h+var_58]
0x18001fee3  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18001fee8  mov     rcx, [rsp+168h+var_60]; void *
0x18001fef0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fef5  mov     [rsp+168h+var_60], r14
0x18001fefd  mov     rcx, [rsp+168h+var_68]; void *
0x18001ff05  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ff0a  mov     [rsp+168h+var_68], r14
0x18001ff12  mov     rcx, [rsp+168h+var_70]; void *
0x18001ff1a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ff1f  mov     [rsp+168h+var_70], r14
0x18001ff27  lea     rcx, [rsp+168h+var_98]
0x18001ff2f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ff34  lea     rcx, [rsp+168h+var_B8]
0x18001ff3c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ff41  nop
0x18001ff42  lea     rcx, [rsp+168h+var_F8]
0x18001ff47  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ff4c  nop
0x18001ff4d  lea     rcx, [rsp+168h+var_D8]
0x18001ff55  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ff5a  mov     rax, [rdi]
0x18001ff5d  mov     rbx, [rax+8]
0x18001ff61  add     rbx, 10h
0x18001ff65  lea     rcx, [rdi+10h]
0x18001ff69  lea     rdx, [rsp+168h+var_108]
0x18001ff6e  call    ??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](ulong const &)
0x18001ff73  cmp     qword ptr [rbx+18h], 7
0x18001ff78  jbe     short loc_18001FF7F
0x18001ff7a  mov     rcx, [rbx]
0x18001ff7d  jmp     short loc_18001FF82
0x18001ff7f  mov     rcx, rbx
0x18001ff82  mov     [rsp+168h+var_100], rcx
0x18001ff87  lea     rdx, [rsp+168h+var_100]
0x18001ff8c  mov     rcx, rax
0x18001ff8f  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x18001ff94  mov     [rax], r14
0x18001ff97  cmp     qword ptr [rbx+18h], 7
0x18001ff9c  jbe     short loc_18001FFA1
0x18001ff9e  mov     rbx, [rbx]
0x18001ffa1  mov     [rsp+168h+var_100], rbx
0x18001ffa6  lea     rcx, [rdi+20h]
0x18001ffaa  lea     rdx, [rsp+168h+var_100]
0x18001ffaf  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x18001ffb4  mov     [rax], r14
0x18001ffb7  xor     eax, eax
0x18001ffb9  jmp     short loc_18001FFC0
0x18001ffbb  mov     eax, 8007000Eh
0x18001ffc0  mov     rcx, [rsp+168h+var_28]
0x18001ffc8  xor     rcx, rsp; StackCookie
0x18001ffcb  call    __security_check_cookie
0x18001ffd0  mov     rbx, [rsp+168h+arg_18]
0x18001ffd8  add     rsp, 150h
0x18001ffdf  pop     r14
0x18001ffe1  pop     rdi
0x18001ffe2  pop     rsi
0x18001ffe3  retn
```
