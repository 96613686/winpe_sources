# Microsoft::Windows::Performance::CCvDDCache::AddFailure(ushort const *,ulong)

- ea: `0x180020e38`
- end: `0x180021025`
- name: `?AddFailure@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGK@Z`
- size: `493`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180021250`

## callees

- `0x180001b90`
- `0x180001bf8`
- `0x18000a924`
- `0x1800103a8`
- `0x18001f074`
- `0x18001ff78`
- `0x180020760`
- `0x1800208a0`
- `0x180020e38`
- `0x180027b70`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Performance::CCvDDCache::AddFailure(
        Microsoft::Windows::Performance::CCvDDCache *this,
        const unsigned __int16 *a2,
        int a3)
{
  __int64 v6; // r8
  __int64 v7; // rdx
  _QWORD *v8; // rbx
  __int64 v9; // rax
  _QWORD *v10; // rcx
  int v12; // [rsp+60h] [rbp-108h] BYREF
  _QWORD *v13; // [rsp+68h] [rbp-100h] BYREF
  _OWORD v14[2]; // [rsp+70h] [rbp-F8h] BYREF
  _OWORD v15[2]; // [rsp+90h] [rbp-D8h] BYREF
  _BYTE v16[32]; // [rsp+B0h] [rbp-B8h] BYREF
  _BYTE v17[40]; // [rsp+D0h] [rbp-98h] BYREF
  void *v18; // [rsp+F8h] [rbp-70h]
  void *v19; // [rsp+100h] [rbp-68h]
  void *v20; // [rsp+108h] [rbp-60h]
  _BYTE v21[48]; // [rsp+110h] [rbp-58h] BYREF

  v12 = a3;
  memset(v15, 0, sizeof(v15));
  std::wstring::_Construct<1,unsigned short const *>(v15, &String2, 0);
  memset(v14, 0, sizeof(v14));
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  std::wstring::_Construct<1,unsigned short const *>(v14, a2, v6);
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
  std::vector<char>::~vector<char>(v21);
  operator delete(v20);
  v20 = 0;
  operator delete(v19);
  v19 = 0;
  operator delete(v18);
  v18 = 0;
  std::wstring::~wstring(v17);
  std::wstring::~wstring(v16);
  std::wstring::~wstring(v14);
  std::wstring::~wstring(v15);
  v8 = (_QWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 16LL);
  v9 = std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](
         (char *)this + 16,
         &v12);
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
               (char *)this + 32,
               &v13) = 0;
  return 0;
}

```

## disassembly

```asm
0x180020e38  mov     [rsp+arg_18], rbx
0x180020e3d  push    rsi
0x180020e3e  push    rdi
0x180020e3f  push    r14
0x180020e41  sub     rsp, 150h
0x180020e48  mov     rax, cs:__security_cookie
0x180020e4f  xor     rax, rsp
0x180020e52  mov     [rsp+168h+var_28], rax
0x180020e5a  mov     esi, r8d
0x180020e5d  mov     rbx, rdx
0x180020e60  mov     rdi, rcx
0x180020e63  mov     [rsp+168h+var_108], r8d
0x180020e68  xorps   xmm0, xmm0
0x180020e6b  movups  [rsp+168h+var_D8], xmm0
0x180020e73  xorps   xmm1, xmm1
0x180020e76  movdqu  [rsp+168h+var_C8], xmm1
0x180020e7f  xor     r8d, r8d
0x180020e82  lea     rdx, String2
0x180020e89  lea     rcx, [rsp+168h+var_D8]
0x180020e91  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180020e96  nop
0x180020e97  xorps   xmm0, xmm0
0x180020e9a  movups  [rsp+168h+var_F8], xmm0
0x180020e9f  xorps   xmm1, xmm1
0x180020ea2  movdqu  [rsp+168h+var_E8], xmm1
0x180020eab  or      r8, 0FFFFFFFFFFFFFFFFh
0x180020eaf  xor     r14d, r14d
0x180020eb2  inc     r8
0x180020eb5  cmp     [rbx+r8*2], r14w
0x180020eba  jnz     short loc_180020EB2
0x180020ebc  mov     rdx, rbx
0x180020ebf  lea     rcx, [rsp+168h+var_F8]
0x180020ec4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180020ec9  nop
0x180020eca  mov     [rsp+168h+var_110], r14b
0x180020ecf  mov     [rsp+168h+var_118], r14
0x180020ed4  mov     [rsp+168h+var_120], r14d
0x180020ed9  mov     [rsp+168h+var_128], r14d
0x180020ede  mov     [rsp+168h+var_130], esi
0x180020ee2  mov     [rsp+168h+var_138], r14
0x180020ee7  mov     [rsp+168h+var_140], r14
0x180020eec  mov     [rsp+168h+var_148], r14
0x180020ef1  xor     r9d, r9d
0x180020ef4  lea     r8, [rsp+168h+var_D8]
0x180020efc  lea     rdx, [rsp+168h+var_F8]
0x180020f01  lea     rcx, [rsp+168h+var_B8]
0x180020f09  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::wstring const &,std::wstring const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)
0x180020f0e  nop
0x180020f0f  mov     rdx, rax
0x180020f12  mov     rcx, rdi
0x180020f15  call    ?push_back@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAX$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)
0x180020f1a  nop
0x180020f1b  lea     rcx, [rsp+168h+var_58]
0x180020f23  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180020f28  mov     rcx, [rsp+168h+var_60]; void *
0x180020f30  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020f35  mov     [rsp+168h+var_60], r14
0x180020f3d  mov     rcx, [rsp+168h+var_68]; void *
0x180020f45  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020f4a  mov     [rsp+168h+var_68], r14
0x180020f52  mov     rcx, [rsp+168h+var_70]; void *
0x180020f5a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020f5f  mov     [rsp+168h+var_70], r14
0x180020f67  lea     rcx, [rsp+168h+var_98]
0x180020f6f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020f74  lea     rcx, [rsp+168h+var_B8]
0x180020f7c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020f81  nop
0x180020f82  lea     rcx, [rsp+168h+var_F8]
0x180020f87  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020f8c  nop
0x180020f8d  lea     rcx, [rsp+168h+var_D8]
0x180020f95  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020f9a  mov     rax, [rdi]
0x180020f9d  mov     rbx, [rax+8]
0x180020fa1  add     rbx, 10h
0x180020fa5  lea     rcx, [rdi+10h]
0x180020fa9  lea     rdx, [rsp+168h+var_108]
0x180020fae  call    ??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](ulong const &)
0x180020fb3  cmp     qword ptr [rbx+18h], 7
0x180020fb8  jbe     short loc_180020FBF
0x180020fba  mov     rcx, [rbx]
0x180020fbd  jmp     short loc_180020FC2
0x180020fbf  mov     rcx, rbx
0x180020fc2  mov     [rsp+168h+var_100], rcx
0x180020fc7  lea     rdx, [rsp+168h+var_100]
0x180020fcc  mov     rcx, rax
0x180020fcf  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x180020fd4  mov     [rax], r14
0x180020fd7  cmp     qword ptr [rbx+18h], 7
0x180020fdc  jbe     short loc_180020FE1
0x180020fde  mov     rbx, [rbx]
0x180020fe1  mov     [rsp+168h+var_100], rbx
0x180020fe6  lea     rcx, [rdi+20h]
0x180020fea  lea     rdx, [rsp+168h+var_100]
0x180020fef  call    ??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z; std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)
0x180020ff4  mov     [rax], r14
0x180020ff7  xor     eax, eax
0x180020ff9  jmp     short loc_180021000
0x180020ffb  mov     eax, 8007000Eh
0x180021000  mov     rcx, [rsp+168h+var_28]
0x180021008  xor     rcx, rsp; StackCookie
0x18002100b  call    __security_check_cookie
0x180021010  mov     rbx, [rsp+168h+arg_18]
0x180021018  add     rsp, 150h
0x18002101f  pop     r14
0x180021021  pop     rdi
0x180021022  pop     rsi
0x180021023  retn
```
