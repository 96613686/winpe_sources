# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000d464`
- end: `0x18000d59a`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const wil::FailureInfo *info, unsigned int newSequenceId)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000d698`

## callees

- `0x180009df4`
- `0x180009e6c`
- `0x18000c6b4`
- `0x18000d310`
- `0x18000d330`
- `0x18000d464`
- `0x1800204ee`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d513`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d513`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d521`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d521`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const wil::FailureInfo *info,
        unsigned int newSequenceId)
{
  const wchar_t **p_message; // r14
  unsigned __int64 v6; // rbp
  unsigned __int64 v7; // rbp
  SIZE_T v8; // rbp
  unsigned __int64 *p_stringBufferSize; // rdi
  void *v10; // r14
  void *stringBuffer; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int8 *v13; // rcx
  unsigned __int8 *v14; // rbx
  unsigned __int8 *v15; // rax
  unsigned __int8 *v16; // rax
  unsigned __int8 *v17; // rax

  this->sequenceId = newSequenceId;
  p_message = &this->message;
  this->hr = info->hr;
  this->fileName = 0;
  this->lineNumber = info->uLineNumber;
  this->failureType = info->type;
  this->modulePath = 0;
  this->returnAddress = info->returnAddress;
  this->callerReturnAddress = info->callerReturnAddress;
  this->message = 0;
  v6 = wil::details::ResultStringSize(info->pszMessage);
  v7 = wil::details::ResultStringSize(info->pszFile) + v6;
  v8 = wil::details::ResultStringSize(info->pszModule) + v7;
  p_stringBufferSize = &this->stringBufferSize;
  if ( !this->stringBuffer || *p_stringBufferSize < v8 )
  {
    v10 = wil::details::ProcessHeapAlloc(8u, v8);
    if ( v10 )
    {
      stringBuffer = this->stringBuffer;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, stringBuffer);
      this->stringBuffer = v10;
      *p_stringBufferSize = v8;
    }
    p_message = &this->message;
  }
  v13 = (unsigned __int8 *)this->stringBuffer;
  if ( v13 )
  {
    v14 = &v13[*p_stringBufferSize];
    v15 = wil::details::WriteResultString<char const *>(v13, v14, info->pszFile, &this->fileName);
    v16 = wil::details::WriteResultString<char const *>(v15, v14, info->pszModule, &this->modulePath);
    v17 = wil::details::WriteResultString<unsigned short const *>(v16, v14, info->pszMessage, p_message);
    memset_0(v17, 0, v14 - v17);
  }
}

```

## disassembly

```asm
0x18000d464  push    rbx
0x18000d466  push    rbp
0x18000d467  push    rsi
0x18000d468  push    rdi
0x18000d469  push    r12
0x18000d46b  push    r13
0x18000d46d  push    r14
0x18000d46f  push    r15
0x18000d471  sub     rsp, 28h
0x18000d475  mov     [this+4], newSequenceId
0x18000d479  lea     r14, [this+38h]
0x18000d47d  mov     eax, [info+8]
0x18000d480  mov     rsi, this
0x18000d483  mov     [this+8], eax
0x18000d486  mov     r15, info
0x18000d489  mov     qword ptr [this+10h], 0
0x18000d491  movzx   eax, word ptr [info+40h]
0x18000d495  mov     [this+18h], ax
0x18000d499  mov     al, [info]
0x18000d49b  mov     [this+1Ah], al
0x18000d49e  mov     qword ptr [this+20h], 0
0x18000d4a6  mov     rax, [info+88h]
0x18000d4ad  mov     [this+28h], rax
0x18000d4b1  mov     rax, [info+90h]
0x18000d4b8  mov     [this+30h], rax
0x18000d4bc  mov     qword ptr [r14], 0
0x18000d4c3  mov     this, [info+18h]; psz
0x18000d4c7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000d4cc  mov     this, [r15+38h]; psz
0x18000d4d0  mov     rbp, rax
0x18000d4d3  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000d4d8  mov     this, [r15+80h]; psz
0x18000d4df  add     rbp, rax
0x18000d4e2  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000d4e7  add     rbp, rax
0x18000d4ea  lea     rdi, [rsi+48h]
0x18000d4ee  cmp     qword ptr [rsi+40h], 0
0x18000d4f3  jz      short loc_18000D4FA
0x18000d4f5  cmp     [rdi], rbp
0x18000d4f8  jnb     short loc_18000D532
0x18000d4fa  mov     info, rbp; size
0x18000d4fd  mov     ecx, 8; flags
0x18000d502  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d507  mov     r14, rax
0x18000d50a  test    rax, rax
0x18000d50d  jz      short loc_18000D52E
0x18000d50f  mov     rbx, [rsi+40h]
0x18000d513  call    cs:__imp_GetProcessHeap
0x18000d519  mov     r8, rbx; lpMem
0x18000d51c  xor     edx, edx; dwFlags
0x18000d51e  mov     this, rax; hHeap
0x18000d521  call    cs:__imp_HeapFree
0x18000d527  mov     [rsi+40h], r14
0x18000d52b  mov     [rdi], rbp
0x18000d52e  lea     r14, [rsi+38h]
0x18000d532  mov     this, [rsi+40h]; pStart
0x18000d536  test    this, this
0x18000d539  jz      short loc_18000D589
0x18000d53b  mov     rbx, [rdi]
0x18000d53e  lea     r9, [rsi+10h]; ppszBufferString
0x18000d542  mov     r8, [r15+38h]; pszString
0x18000d546  add     rbx, this
0x18000d549  mov     info, rbx; pEnd
0x18000d54c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000d551  mov     r8, [r15+80h]; pszString
0x18000d558  lea     r9, [rsi+20h]; ppszBufferString
0x18000d55c  mov     info, rbx; pEnd
0x18000d55f  mov     this, rax; pStart
0x18000d562  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000d567  mov     r8, [r15+18h]; pszString
0x18000d56b  mov     r9, r14; ppszBufferString
0x18000d56e  mov     info, rbx; pEnd
0x18000d571  mov     this, rax; pStart
0x18000d574  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000d579  sub     rbx, rax
0x18000d57c  xor     edx, edx; Val
0x18000d57e  mov     r8, rbx; Size
0x18000d581  mov     this, rax; void *
0x18000d584  call    memset_0
0x18000d589  add     rsp, 28h
0x18000d58d  pop     r15
0x18000d58f  pop     r14
0x18000d591  pop     r13
0x18000d593  pop     r12
0x18000d595  pop     rdi
0x18000d596  pop     rsi
0x18000d597  pop     rbp
0x18000d598  pop     rbx
0x18000d599  retn
```
