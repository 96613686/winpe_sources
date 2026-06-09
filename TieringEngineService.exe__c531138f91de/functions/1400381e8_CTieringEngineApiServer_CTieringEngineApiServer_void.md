# CTieringEngineApiServer::~CTieringEngineApiServer(void)

- ea: `0x1400381e8`
- end: `0x14003824a`
- name: `??1CTieringEngineApiServer@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(CTieringEngineApiServer *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400028ac`
- `0x1400029a0`

## callees

- `0x140004a40`
- `0x140038164`
- `0x1400381e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14003823d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14003823d`

## pseudocode

```c
void __fastcall CTieringEngineApiServer::~CTieringEngineApiServer(CTieringEngineApiServer *this)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
  }
  utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,TieringResumeKey>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,TieringResumeKey>>,0>::~_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,TieringResumeKey>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,TieringResumeKey>>,0>((char *)this + 64);
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x1400381e8  push    rbx
0x1400381ea  sub     rsp, 20h
0x1400381ee  mov     rbx, rcx
0x1400381f1  lea     rax, WPP_GLOBAL_Control
0x1400381f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400381ff  cmp     rcx, rax
0x140038202  jz      short loc_140038225
0x140038204  test    byte ptr [rcx+1Ch], 1
0x140038208  jz      short loc_140038225
0x14003820a  cmp     byte ptr [rcx+19h], 4
0x14003820e  jb      short loc_140038225
0x140038210  mov     edx, 0Dh
0x140038215  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x14003821c  mov     rcx, [rcx+10h]
0x140038220  call    WPP_SF_
0x140038225  lea     rcx, [rbx+40h]
0x140038229  call    ??1?$_HashTable@_KU?$pair@$$CB_KVTieringResumeKey@@@utl@@U?$hash@_K@2@U?$equal_to@_K@2@V?$allocator@U?$pair@$$CB_KVTieringResumeKey@@@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,TieringResumeKey>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,TieringResumeKey>>,0>::~_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,TieringResumeKey>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,TieringResumeKey>>,0>(void)
0x14003822e  nop
0x14003822f  lea     rcx, [rbx+10h]; lpCriticalSection
0x140038233  cmp     byte ptr [rcx+28h], 0
0x140038237  jz      short loc_140038244
0x140038239  mov     byte ptr [rcx+28h], 0
0x14003823d  call    cs:__imp_DeleteCriticalSection
0x140038243  nop
0x140038244  add     rsp, 20h
0x140038248  pop     rbx
0x140038249  retn
```
