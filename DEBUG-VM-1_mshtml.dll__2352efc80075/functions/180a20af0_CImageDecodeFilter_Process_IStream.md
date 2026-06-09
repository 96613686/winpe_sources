# CImageDecodeFilter::Process(IStream *)

- ea: `0x180a20af0`
- end: `0x180a20e16`
- name: `?Process@CImageDecodeFilter@@UEAAJPEAUIStream@@@Z`
- size: `806`
- prototype: `__int64 __fastcall(CImageDecodeFilter *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1800e2b08`
- `0x1801af6e0`
- `0x1801cd5ac`
- `0x18022289c`
- `0x18043c328`
- `0x180497b20`
- `0x180497b40`
- `0x1804a31fc`
- `0x1804a3234`
- `0x180a20440`
- `0x180a20af0`
- `0x1810c2c92`
- `0x1810c2cb6`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetExitCodeThread` at `0x180a20da5`
- `KERNEL32!GetExitCodeThread` at `0x180a20da5`
- `KERNEL32!CreateThread` at `0x180a20d17`
- `KERNEL32!CreateThread` at `0x180a20d17`
- `KERNEL32!CreateEventW` at `0x180a20cbd`
- `KERNEL32!CreateEventW` at `0x180a20cdd`
- `KERNEL32!CreateEventW` at `0x180a20cbd`
- `KERNEL32!CreateEventW` at `0x180a20cdd`
- `KERNEL32!CloseHandle` at `0x180a20dae`
- `KERNEL32!CloseHandle` at `0x180a20dbb`
- `KERNEL32!CloseHandle` at `0x180a20dc8`
- `KERNEL32!CloseHandle` at `0x180a20dae`
- `KERNEL32!CloseHandle` at `0x180a20dbb`
- `KERNEL32!CloseHandle` at `0x180a20dc8`
- `KERNEL32!WaitForSingleObject` at `0x180a20d3c`
- `KERNEL32!WaitForSingleObject` at `0x180a20d98`
- `KERNEL32!WaitForSingleObject` at `0x180a20d3c`
- `KERNEL32!WaitForSingleObject` at `0x180a20d98`
- `iertutil!CreateUri` at `0x180a20b7e`
- `iertutil!CreateUri` at `0x180a20b7e`

## pseudocode

```c
__int64 __fastcall CImageDecodeFilter::Process(CImageDecodeFilter *this, struct IStream *a2)
{
  HANDLE v4; // rcx
  CDwnDoc *v5; // rax
  CDwnDoc *v6; // rax
  CBaseFT *v7; // rbx
  unsigned int v8; // esi
  unsigned int v9; // r15d
  const void *v10; // r14
  __int64 *v11; // rcx
  __int64 v12; // rax
  unsigned int v13; // ecx
  struct IDwnInfoManager **v14; // rax
  CBaseFT *v15; // rsi
  CBaseFT *v16; // r14
  CBaseFT *v17; // rcx
  __int64 v18; // rax
  volatile signed __int32 *v19; // rax
  HANDLE EventW; // rax
  HANDLE v21; // rax
  HANDLE v22; // rsi
  DWORD v23; // ebx
  int v24; // eax
  IUri *ppURI; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v27[2]; // [rsp+38h] [rbp-10h] BYREF
  DWORD ExitCode; // [rsp+90h] [rbp+48h] BYREF
  DWORD ThreadId; // [rsp+98h] [rbp+50h] BYREF
  unsigned __int64 v30; // [rsp+A0h] [rbp+58h]
  CBaseFT *v31; // [rsp+A8h] [rbp+60h] BYREF

  ExitCode = -2147467259;
  ThreadId = 0;
  v31 = 0;
  ppURI = 0;
  v27[0] = 0;
  memset_0((char *)this + 80, 0, 0xA8u);
  v4 = g_hProcessHeap;
  *((_QWORD *)this + 15) = a2;
  v5 = (CDwnDoc *)MemoryProtection::HeapAllocClear<1>(v4, 832);
  if ( v5 && (v6 = CDwnDoc::CDwnDoc(v5), (v7 = v6) != 0) )
  {
    *((_QWORD *)this + 11) = v6;
    ExitCode = CreateUri(&LocaleName, 0x3002B81u, 0, &ppURI);
    if ( !ExitCode )
    {
      *((_QWORD *)this + 14) = ppURI;
      if ( *((_DWORD *)this + 5) )
      {
        v8 = 0;
        while ( 2 )
        {
          v9 = 0;
          v10 = (const void *)(*((_QWORD *)this + 3) + 16LL * v8);
          while ( v9 < 7 )
          {
            if ( !memcmp_0((const void *)qword_1811A3930[2 * v9 + 1], v10, 0x10u) )
            {
              v11 = &qword_1811A3930[2 * v9];
              if ( v11 )
              {
                v12 = *((_QWORD *)v7 + 21);
                v13 = v12 & 0xFFFFFFC0 | *(_DWORD *)v11 & 0x3F;
                v30 = __PAIR64__(HIDWORD(v12), v13);
                BYTE3(v30) = HIBYTE(v13) | 8;
                BYTE1(v30) = BYTE1(v13) | 1;
                *((_QWORD *)v7 + 21) = v30;
                v14 = (struct IDwnInfoManager **)TSmartPointer<IDwnInfoManager>::operator&(v27);
                ExitCode = GetDwnInfoManager(v14);
                if ( (ExitCode & 0x80000000) == 0 )
                {
                  ExitCode = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, char *, CBaseFT **))(*(_QWORD *)v27[0] + 24LL))(
                               v27[0],
                               1,
                               0,
                               (char *)this + 80,
                               &v31);
                  if ( (ExitCode & 0x80000000) == 0 )
                  {
                    v15 = v31;
                    v16 = 0;
                    v17 = v31;
                    *((_QWORD *)this + 6) = v31;
                    CBaseFT::EnterCriticalSection(v17);
                    v18 = *((_QWORD *)v15 + 12);
                    if ( v18 )
                    {
                      v19 = *(volatile signed __int32 **)(v18 + 280);
                      if ( v19 )
                      {
                        v16 = (CBaseFT *)v19;
                        _InterlockedAdd(v19 + 4, 1u);
                      }
                    }
                    CBaseFT::LeaveCriticalSection(v15);
                    EventW = CreateEventW(0, 0, 0, 0);
                    *((_QWORD *)this + 34) = EventW;
                    if ( EventW )
                    {
                      v21 = CreateEventW(0, 0, 0, 0);
                      *((_QWORD *)this + 35) = v21;
                      if ( v21 )
                      {
                        *((_DWORD *)this + 66) = 0;
                        v22 = CreateThread(0, 0, CImageDecodeFilter::ThreadProc, (char *)this - 24, 0, &ThreadId);
                        if ( v22 )
                        {
                          if ( *((_DWORD *)this + 66) != 2 )
                          {
                            do
                            {
                              WaitForSingleObject(*((HANDLE *)this + 34), 0xFFFFFFFF);
                              while ( 1 )
                              {
                                v24 = *((_DWORD *)this + 66);
                                if ( v24 != 1 )
                                  break;
                                *((_DWORD *)this + 66) = 0;
                                CImageDecodeFilter::ImageCallback((CImageDecodeFilter *)((char *)this - 24));
                              }
                            }
                            while ( v24 != 2 );
                          }
                          WaitForSingleObject(v22, 0xFFFFFFFF);
                          GetExitCodeThread(v22, &ExitCode);
                          CloseHandle(v22);
                        }
                        CloseHandle(*((HANDLE *)this + 35));
                      }
                      CloseHandle(*((HANDLE *)this + 34));
                    }
                    if ( v16 )
                      CBaseFT::Release(v16);
                    if ( v31 )
                      CBaseFT::Release(v31);
                  }
                }
                goto LABEL_23;
              }
              break;
            }
            ++v9;
          }
          if ( ++v8 < *((_DWORD *)this + 5) )
            continue;
          break;
        }
      }
      ExitCode = -2147467259;
    }
LABEL_23:
    CBaseFT::Release(v7);
    ReleaseInterface((struct IUnknown *)ppURI);
    v23 = ExitCode;
  }
  else
  {
    v23 = -2147024882;
    ExitCode = -2147024882;
  }
  TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(v27);
  return v23;
}

```

## disassembly

```asm
0x180a20af0  push    rbp
0x180a20af2  push    rbx
0x180a20af3  push    rsi
0x180a20af4  push    rdi
0x180a20af5  push    r12
0x180a20af7  push    r13
0x180a20af9  push    r14
0x180a20afb  push    r15
0x180a20afd  mov     rbp, rsp
0x180a20b00  sub     rsp, 48h
0x180a20b04  xor     r12d, r12d
0x180a20b07  mov     [rbp+ExitCode], 80004005h
0x180a20b0e  mov     rbx, rdx
0x180a20b11  mov     [rbp+ThreadId], r12d
0x180a20b15  mov     rdi, rcx
0x180a20b18  mov     [rbp+arg_18], r12
0x180a20b1c  xor     edx, edx; Val
0x180a20b1e  mov     [rbp+ppURI], r12
0x180a20b22  add     rcx, 50h ; 'P'; void *
0x180a20b26  mov     [rbp+var_10], r12
0x180a20b2a  mov     r8d, 0A8h; Size
0x180a20b30  call    memset_0
0x180a20b35  mov     rcx, cs:g_hProcessHeap
0x180a20b3c  mov     edx, 340h
0x180a20b41  mov     [rdi+78h], rbx
0x180a20b45  call    ??$HeapAllocClear@$00@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAllocClear<1>(void *,unsigned __int64)
0x180a20b4a  test    rax, rax
0x180a20b4d  jz      loc_180A20DF2
0x180a20b53  mov     rcx, rax; this
0x180a20b56  call    ??0CDwnDoc@@QEAA@XZ; CDwnDoc::CDwnDoc(void)
0x180a20b5b  mov     rbx, rax
0x180a20b5e  test    rax, rax
0x180a20b61  jz      loc_180A20DF2
0x180a20b67  lea     r9, [rbp+ppURI]; ppURI
0x180a20b6b  mov     [rdi+58h], rax
0x180a20b6f  xor     r8d, r8d; dwReserved
0x180a20b72  lea     rcx, LocaleName; pwzURI
0x180a20b79  mov     edx, 3002B81h; dwFlags
0x180a20b7e  call    cs:__imp_CreateUri
0x180a20b84  mov     [rbp+ExitCode], eax
0x180a20b87  test    eax, eax
0x180a20b89  jnz     loc_180A20D59
0x180a20b8f  mov     rax, [rbp+ppURI]
0x180a20b93  mov     [rdi+70h], rax
0x180a20b97  cmp     [rdi+14h], r12d
0x180a20b9b  jbe     loc_180A20D52
0x180a20ba1  mov     esi, r12d
0x180a20ba4  lea     rax, qword_1811A3930
0x180a20bab  mov     r14d, esi
0x180a20bae  mov     r15d, r12d
0x180a20bb1  shl     r14, 4
0x180a20bb5  add     r14, [rdi+18h]
0x180a20bb9  cmp     r15d, 7
0x180a20bbd  jnb     loc_180A20D44
0x180a20bc3  mov     r12d, r15d
0x180a20bc6  mov     r8d, 10h; Size
0x180a20bcc  add     r12, r12
0x180a20bcf  mov     rdx, r14; Buf2
0x180a20bd2  mov     rcx, [rax+r12*8+8]; Buf1
0x180a20bd7  call    memcmp_0
0x180a20bdc  test    eax, eax
0x180a20bde  lea     rax, qword_1811A3930
0x180a20be5  jz      short loc_180A20BEC
0x180a20be7  inc     r15d
0x180a20bea  jmp     short loc_180A20BB9
0x180a20bec  lea     rcx, [rax+r12*8]
0x180a20bf0  xor     r12d, r12d
0x180a20bf3  test    rcx, rcx
0x180a20bf6  jz      loc_180A20D47
0x180a20bfc  mov     ecx, [rcx]
0x180a20bfe  mov     rax, [rbx+0A8h]
0x180a20c05  and     ecx, 3Fh
0x180a20c08  mov     [rbp+arg_10], rax
0x180a20c0c  and     eax, 0FFFFFFC0h
0x180a20c0f  or      ecx, eax
0x180a20c11  mov     dword ptr [rbp+arg_10], ecx
0x180a20c14  or      byte ptr [rbp+arg_10+3], 8
0x180a20c18  shr     ecx, 8
0x180a20c1b  or      cl, 1
0x180a20c1e  mov     byte ptr [rbp+arg_10+1], cl
0x180a20c21  lea     rcx, [rbp+var_10]
0x180a20c25  mov     rax, [rbp+arg_10]
0x180a20c29  mov     [rbx+0A8h], rax
0x180a20c30  call    ??I?$TSmartPointer@UIDwnInfoManager@@@@QEAAPEAPEAUIDwnInfoManager@@XZ; TSmartPointer<IDwnInfoManager>::operator&(void)
0x180a20c35  mov     rcx, rax; struct IDwnInfoManager **
0x180a20c38  call    ?GetDwnInfoManager@@YAJPEAPEAUIDwnInfoManager@@@Z; GetDwnInfoManager(IDwnInfoManager * *)
0x180a20c3d  mov     [rbp+ExitCode], eax
0x180a20c40  test    eax, eax
0x180a20c42  js      loc_180A20D59
0x180a20c48  mov     rcx, [rbp+var_10]
0x180a20c4c  lea     rdx, [rbp+arg_18]
0x180a20c50  mov     qword ptr [rsp+48h+dwCreationFlags], rdx
0x180a20c55  lea     r13d, [r12+1]
0x180a20c5a  lea     r9, [rdi+50h]
0x180a20c5e  xor     r8d, r8d
0x180a20c61  mov     edx, r13d
0x180a20c64  mov     rax, [rcx]
0x180a20c67  mov     rax, [rax+18h]
0x180a20c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a20c70  mov     [rbp+ExitCode], eax
0x180a20c73  test    eax, eax
0x180a20c75  js      loc_180A20D59
0x180a20c7b  mov     rsi, [rbp+arg_18]
0x180a20c7f  mov     r14d, r12d
0x180a20c82  mov     rcx, rsi; this
0x180a20c85  mov     [rdi+30h], rsi
0x180a20c89  call    ?EnterCriticalSection@CBaseFT@@QEAAXXZ; CBaseFT::EnterCriticalSection(void)
0x180a20c8e  mov     rax, [rsi+60h]
0x180a20c92  test    rax, rax
0x180a20c95  jz      short loc_180A20CAB
0x180a20c97  mov     rax, [rax+118h]
0x180a20c9e  test    rax, rax
0x180a20ca1  jz      short loc_180A20CAB
0x180a20ca3  mov     r14, rax
0x180a20ca6  lock add [rax+10h], r13d
0x180a20cab  mov     rcx, rsi; this
0x180a20cae  call    ?LeaveCriticalSection@CBaseFT@@QEAAXXZ; CBaseFT::LeaveCriticalSection(void)
0x180a20cb3  xor     r9d, r9d; lpName
0x180a20cb6  xor     r8d, r8d; bInitialState
0x180a20cb9  xor     edx, edx; bManualReset
0x180a20cbb  xor     ecx, ecx; lpEventAttributes
0x180a20cbd  call    cs:__imp_CreateEventW
0x180a20cc3  mov     [rdi+110h], rax
0x180a20cca  test    rax, rax
0x180a20ccd  jz      loc_180A20DCE
0x180a20cd3  xor     r9d, r9d; lpName
0x180a20cd6  xor     r8d, r8d; bInitialState
0x180a20cd9  xor     edx, edx; bManualReset
0x180a20cdb  xor     ecx, ecx; lpEventAttributes
0x180a20cdd  call    cs:__imp_CreateEventW
0x180a20ce3  mov     [rdi+118h], rax
0x180a20cea  test    rax, rax
0x180a20ced  jz      loc_180A20DC1
0x180a20cf3  lea     rax, [rbp+ThreadId]
0x180a20cf7  mov     [rdi+108h], r12d
0x180a20cfe  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x180a20d03  lea     r9, [rdi-18h]; lpParameter
0x180a20d07  lea     r8, ?ThreadProc@CImageDecodeFilter@@CAKPEAX@Z; lpStartAddress
0x180a20d0e  mov     [rsp+48h+dwCreationFlags], r12d; dwCreationFlags
0x180a20d13  xor     edx, edx; dwStackSize
0x180a20d15  xor     ecx, ecx; lpThreadAttributes
0x180a20d17  call    cs:__imp_CreateThread
0x180a20d1d  mov     rsi, rax
0x180a20d20  test    rax, rax
0x180a20d23  jz      loc_180A20DB4
0x180a20d29  cmp     dword ptr [rdi+108h], 2
0x180a20d30  jz      short loc_180A20D92
0x180a20d32  mov     rcx, [rdi+110h]; hHandle
0x180a20d39  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180a20d3c  call    cs:__imp_WaitForSingleObject
0x180a20d42  jmp     short loc_180A20D82
0x180a20d44  xor     r12d, r12d
0x180a20d47  inc     esi
0x180a20d49  cmp     esi, [rdi+14h]
0x180a20d4c  jb      loc_180A20BAB
0x180a20d52  mov     [rbp+ExitCode], 80004005h
0x180a20d59  mov     rcx, rbx; this
0x180a20d5c  call    ?Release@CBaseFT@@QEAAKXZ; CBaseFT::Release(void)
0x180a20d61  mov     rcx, [rbp+ppURI]; struct IUnknown *
0x180a20d65  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180a20d6a  mov     ebx, [rbp+ExitCode]
0x180a20d6d  jmp     loc_180A20DFA
0x180a20d72  lea     rcx, [rdi-18h]; this
0x180a20d76  mov     [rdi+108h], r12d
0x180a20d7d  call    ?ImageCallback@CImageDecodeFilter@@AEAAXXZ; CImageDecodeFilter::ImageCallback(void)
0x180a20d82  mov     eax, [rdi+108h]
0x180a20d88  cmp     eax, r13d
0x180a20d8b  jz      short loc_180A20D72
0x180a20d8d  cmp     eax, 2
0x180a20d90  jnz     short loc_180A20D32
0x180a20d92  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180a20d95  mov     rcx, rsi; hHandle
0x180a20d98  call    cs:__imp_WaitForSingleObject
0x180a20d9e  lea     rdx, [rbp+ExitCode]; lpExitCode
0x180a20da2  mov     rcx, rsi; hThread
0x180a20da5  call    cs:__imp_GetExitCodeThread
0x180a20dab  mov     rcx, rsi; hObject
0x180a20dae  call    cs:__imp_CloseHandle
0x180a20db4  mov     rcx, [rdi+118h]; hObject
0x180a20dbb  call    cs:__imp_CloseHandle
0x180a20dc1  mov     rcx, [rdi+110h]; hObject
0x180a20dc8  call    cs:__imp_CloseHandle
0x180a20dce  test    r14, r14
0x180a20dd1  jz      short loc_180A20DDB
0x180a20dd3  mov     rcx, r14; this
0x180a20dd6  call    ?Release@CBaseFT@@QEAAKXZ; CBaseFT::Release(void)
0x180a20ddb  mov     rcx, [rbp+arg_18]; this
0x180a20ddf  test    rcx, rcx
0x180a20de2  jz      loc_180A20D59
0x180a20de8  call    ?Release@CBaseFT@@QEAAKXZ; CBaseFT::Release(void)
0x180a20ded  jmp     loc_180A20D59
0x180a20df2  mov     ebx, 8007000Eh
0x180a20df7  mov     [rbp+ExitCode], ebx
0x180a20dfa  lea     rcx, [rbp+var_10]; void *
0x180a20dfe  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x180a20e03  mov     eax, ebx
0x180a20e05  add     rsp, 48h
0x180a20e09  pop     r15
0x180a20e0b  pop     r14
0x180a20e0d  pop     r13
0x180a20e0f  pop     r12
0x180a20e11  pop     rdi
0x180a20e12  pop     rsi
0x180a20e13  pop     rbx
0x180a20e14  pop     rbp
0x180a20e15  retn
```
