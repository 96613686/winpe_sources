# Threading::ThreadEntered::Initialize(bool)

- ea: `0x18003a46c`
- end: `0x18003a57b`
- name: `?Initialize@ThreadEntered@Threading@@AEAAX_N@Z`
- size: `271`
- prototype: `void __fastcall(Threading::ThreadEntered *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800395d8`

## callees

- `0x180006ee0`
- `0x18000ec98`
- `0x180038e0c`
- `0x1800395ac`
- `0x180039b40`
- `0x18003a46c`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a4a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a4a6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003a48e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003a48e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003a4c2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003a4c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Threading::ThreadEntered::Initialize(Threading::ThreadEntered *this, char a2)
{
  signed __int32 v4; // ebx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v8[16]; // [rsp+30h] [rbp-68h] BYREF
  _OWORD pExceptionObject[2]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v10; // [rsp+60h] [rbp-38h]

  if ( !byte_180109330 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_8f71bf2a86f63c0585a15c2236b3f2b4_Traceguids);
    memset(pExceptionObject, 0, sizeof(pExceptionObject));
    v10 = 0;
    ThreadCancelledException::ThreadCancelledException((ThreadCancelledException *)pExceptionObject);
    throw (ThreadCancelledException *)pExceptionObject;
  }
  if ( !TlsGetValue(dword_1801079C8) )
  {
    v4 = _InterlockedIncrement(&dword_1801079C0);
    *((_DWORD *)this + 18) = GetCurrentThreadId();
    *((_DWORD *)this + 19) = v4;
    *((_BYTE *)this + 80) = a2;
    TlsSetValue(dword_1801079C8, (char *)this + 72);
    v5 = Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::operator->();
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 48LL))(v5, &v7);
    *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned __int64,Private::ThreadInfo *,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,Private::ThreadInfo *>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                             *(_QWORD *)(v6 + 8),
                             (__int64)v8,
                             (_QWORD *)this + 9)
              + 24LL) = (char *)this + 72;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
  }
}

```

## disassembly

```asm
0x18003a46c  push    rbx
0x18003a46e  push    rbp
0x18003a46f  push    rsi
0x18003a470  push    rdi
0x18003a471  sub     rsp, 78h
0x18003a475  mov     bpl, dl
0x18003a478  mov     rsi, rcx
0x18003a47b  cmp     cs:byte_180109330, 0
0x18003a482  jz      loc_18003A51D
0x18003a488  mov     ecx, cs:dword_1801079C8; dwTlsIndex
0x18003a48e  call    cs:__imp_TlsGetValue
0x18003a494  test    rax, rax
0x18003a497  jnz     short loc_18003A514
0x18003a499  lea     ebx, [rax+1]
0x18003a49c  lock xadd cs:dword_1801079C0, ebx
0x18003a4a4  inc     ebx
0x18003a4a6  call    cs:__imp_GetCurrentThreadId
0x18003a4ac  lea     rdi, [rsi+48h]
0x18003a4b0  mov     [rdi], eax
0x18003a4b2  mov     [rdi+4], ebx
0x18003a4b5  mov     [rsi+50h], bpl
0x18003a4b9  mov     rdx, rdi; lpTlsValue
0x18003a4bc  mov     ecx, cs:dword_1801079C8; dwTlsIndex
0x18003a4c2  call    cs:__imp_TlsSetValue
0x18003a4c8  call    ??C?$Global@V?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@@@QEAAPEAV?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@XZ; Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::operator->(void)
0x18003a4cd  mov     r8, rax
0x18003a4d0  mov     rcx, [rax]
0x18003a4d3  mov     rax, [rcx+30h]
0x18003a4d7  lea     rdx, [rsp+98h+var_78]
0x18003a4dc  mov     rcx, r8
0x18003a4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4e4  nop
0x18003a4e5  mov     r8, rdi
0x18003a4e8  lea     rdx, [rsp+98h+var_68]
0x18003a4ed  mov     rcx, [rax+8]
0x18003a4f1  call    ??$_Try_emplace@AEB_K$$V@?$_Hash@V?$_Umap_traits@_KPEAUThreadInfo@Private@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,Private::ThreadInfo *,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,Private::ThreadInfo *>>,0>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x18003a4f6  mov     rcx, [rax]
0x18003a4f9  mov     [rcx+18h], rdi
0x18003a4fd  mov     rcx, [rsp+98h+var_78]
0x18003a502  test    rcx, rcx
0x18003a505  jz      short loc_18003A514
0x18003a507  mov     rax, [rcx]
0x18003a50a  mov     rax, [rax+18h]
0x18003a50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a513  nop
0x18003a514  add     rsp, 78h
0x18003a518  pop     rdi
0x18003a519  pop     rsi
0x18003a51a  pop     rbp
0x18003a51b  pop     rbx
0x18003a51c  retn
0x18003a51d  lea     rax, WPP_GLOBAL_Control
0x18003a524  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a52b  cmp     rcx, rax
0x18003a52e  jz      short loc_18003A54B
0x18003a530  test    byte ptr [rcx+1Ch], 1
0x18003a534  jz      short loc_18003A54B
0x18003a536  mov     edx, 13h
0x18003a53b  lea     r8, WPP_8f71bf2a86f63c0585a15c2236b3f2b4_Traceguids
0x18003a542  mov     rcx, [rcx+10h]
0x18003a546  call    WPP_SF_
0x18003a54b  xorps   xmm0, xmm0
0x18003a54e  xor     eax, eax
0x18003a550  movups  [rsp+98h+pExceptionObject], xmm0
0x18003a555  movups  [rsp+98h+var_48], xmm0
0x18003a55a  mov     [rsp+98h+var_38], rax
0x18003a55f  lea     rcx, [rsp+98h+pExceptionObject]; this
0x18003a564  call    ??0ThreadCancelledException@@QEAA@XZ; ThreadCancelledException::ThreadCancelledException(void)
0x18003a569  lea     rdx, _TI4?AVThreadCancelledException@@; pThrowInfo
0x18003a570  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18003a575  call    _CxxThrowException_0
```
