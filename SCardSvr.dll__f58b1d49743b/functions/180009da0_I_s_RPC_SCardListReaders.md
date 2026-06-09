# I_s_RPC_SCardListReaders

- ea: `0x180009da0`
- end: `0x18000a2ae`
- name: `I_s_RPC_SCardListReaders`
- size: `1294`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000e7f0`

## callees

- `0x180009190`
- `0x180009d80`
- `0x180009da0`
- `0x18000a2c0`
- `0x18000c250`
- `0x18000cf60`
- `0x18000d190`
- `0x180019bc4`
- `0x18001c330`
- `0x18001c370`
- `0x180023168`
- `0x180023174`
- `0x180023276`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a1b8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a1b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a130`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a130`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a11f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a11f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a296`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a19e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a19e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180009e02`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180009e19`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180009e02`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180009e19`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000a0bb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000a0bb`
- `KERNEL32!lstrcmpiW` at `0x180009fa2`
- `KERNEL32!lstrcmpiW` at `0x180009fa2`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall I_s_RPC_SCardListReaders(
        LPVOID *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        _QWORD *a4,
        _DWORD *a5)
{
  char *v8; // r13
  unsigned int v9; // ebx
  int v10; // ebx
  const unsigned __int16 *i; // rax
  unsigned int v12; // ebx
  char *v13; // rax
  char *v14; // rbx
  unsigned int v15; // r12d
  const unsigned __int16 *String; // rax
  const WCHAR *v17; // r15
  void *v18; // r13
  struct CCriticalSectionObject *v19; // rbx
  unsigned int v20; // edi
  CReader *v21; // rsi
  const WCHAR *v22; // rdx
  unsigned int v23; // eax
  char *v24; // rax
  const unsigned __int8 *v25; // rcx
  const unsigned __int16 *v26; // r9
  __int64 **v27; // rdi
  void *v28; // rax
  __int64 v29; // rbx
  HANDLE ProcessHeap; // rax
  void *v31; // rax
  void *v32; // r13
  const WCHAR *v33; // rdx
  _DWORD *v34; // rsi
  int v37; // [rsp+30h] [rbp-C8h]
  ulong v38; // [rsp+34h] [rbp-C4h]
  __int64 **v39; // [rsp+38h] [rbp-C0h]
  int v40; // [rsp+40h] [rbp-B8h]
  ulong v41; // [rsp+44h] [rbp-B4h] BYREF
  ulong v42; // [rsp+48h] [rbp-B0h] BYREF
  ulong v43; // [rsp+4Ch] [rbp-ACh] BYREF
  ulong v44; // [rsp+50h] [rbp-A8h] BYREF
  ulong v45; // [rsp+54h] [rbp-A4h] BYREF
  ulong v46; // [rsp+58h] [rbp-A0h] BYREF
  ulong v47; // [rsp+5Ch] [rbp-9Ch] BYREF
  ulong pExceptionObject; // [rsp+60h] [rbp-98h] BYREF
  void *Src; // [rsp+68h] [rbp-90h]
  void **v50; // [rsp+70h] [rbp-88h]
  char *v51; // [rsp+78h] [rbp-80h]
  __int64 v52; // [rsp+80h] [rbp-78h]
  const unsigned __int16 *v53; // [rsp+88h] [rbp-70h]
  ulong v54; // [rsp+90h] [rbp-68h] BYREF
  ulong v55; // [rsp+94h] [rbp-64h] BYREF
  char *v56; // [rsp+98h] [rbp-60h]
  LPVOID *v57; // [rsp+A0h] [rbp-58h]
  char *v58; // [rsp+A8h] [rbp-50h]
  LPVOID *v59; // [rsp+B0h] [rbp-48h]
  _DWORD *v60; // [rsp+B8h] [rbp-40h]
  struct CCriticalSectionObject *v61; // [rsp+C0h] [rbp-38h]
  char *v62; // [rsp+C8h] [rbp-30h]
  LPVOID *v63; // [rsp+100h] [rbp+8h]

  v63 = a1;
  v57 = a1;
  v38 = 0;
  v50 = &CBuffer::`vftable';
  v8 = 0;
  Src = 0;
  v51 = 0;
  v52 = 0;
  if ( !TlsSetValue(dwTlsIndex, a1[9]) || !TlsSetValue(dword_18004B240, *a1) )
    GetLastError();
  try
  {
    _InterlockedExchange(&g_fExtendShutdownTimer, 1);
    v60 = a1 + 10;
    CMutex::Grab((CMutex *)(a1 + 10));
    v59 = a1;
    if ( !a2 || (v9 = a3 >> 1, v9 < 2) || a2[v9 - 1] || a2[v9 - 2] )
    {
      pExceptionObject = -2146435055;
      throw &pExceptionObject;
    }
    v10 = 0;
    for ( i = FirstString(a2); i; i = NextString(i) )
      ++v10;
    v12 = 4 * v10;
    if ( v12 )
    {
      v13 = (char *)operator new[](v12);
      v8 = v13;
      Src = v13;
      if ( !v13 )
      {
        v41 = 14;
        throw &v41;
      }
      v51 = v13;
      HIDWORD(v52) = v12;
    }
    LODWORD(v52) = v12;
    v14 = v8;
    v58 = v8;
    v37 = 0;
    v15 = 0;
    v40 = 0;
    String = FirstString(a2);
    while ( 1 )
    {
      v17 = String;
      v53 = String;
      if ( !String )
        break;
      v56 = &v14[4 * v15];
      *(_DWORD *)v56 = 0;
      try
      {
        v39 = 0;
        v18 = v63[22];
        v19 = g_pcsControlLocks;
        v61 = g_pcsControlLocks;
        (**(void (__fastcall ***)(struct CCriticalSectionObject *, _QWORD, _QWORD))g_pcsControlLocks)(
          g_pcsControlLocks,
          0,
          0);
        v23 = HIDWORD(qword_18004B0C8);
        v20 = HIDWORD(qword_18004B0C8);
        while ( 1 )
        {
          do
          {
            if ( !v20 )
            {
              v44 = -2146435063;
              throw &v44;
            }
            --v20;
          }
          while ( v23 <= v20 );
          _mm_lfence();
          v21 = (CReader *)*((_QWORD *)qword_18004B0D0 + (int)v20);
          if ( v21 )
          {
            v22 = *((_DWORD *)v21 + 7) ? (const WCHAR *)*((_QWORD *)v21 + 2) : &Data;
            if ( !lstrcmpiW(v17, v22) )
              break;
          }
          v23 = HIDWORD(qword_18004B0C8);
        }
        if ( (*(__int64 (__fastcall **)(CReader *))(*(_QWORD *)v21 + 56LL))(v21) )
        {
          if ( v18 )
          {
            v28 = (void *)(*(__int64 (__fastcall **)(CReader *))(*(_QWORD *)v21 + 56LL))(v21);
            if ( !EqualSid(v28, v18) )
            {
              v42 = -2146435063;
              throw &v42;
            }
          }
        }
        v24 = (char *)operator new(0x20u);
        v27 = (__int64 **)v24;
        v62 = v24;
        if ( v24 )
        {
          *(_OWORD *)(v24 + 8) = 0;
          *((_DWORD *)v24 + 6) = 0;
          *(_QWORD *)v24 = CReader::ReaderProxy(v21);
        }
        else
        {
          v27 = 0;
        }
        if ( !v27 )
        {
          CalaisError(v25, 0xCBu, 0, v26);
          v43 = -2146435066;
          throw &v43;
        }
        (*(void (__fastcall **)(struct CCriticalSectionObject *))(*(_QWORD *)v19 + 8LL))(v19);
        v39 = v27;
        if ( (unsigned __int8)CReaderProxy::AvailabilityStatus(*v27) < 9u )
        {
          *(_DWORD *)v56 = 1;
          ++v37;
        }
        CReaderProxy::Release((CReaderProxy *)*v27);
        operator delete(v27);
        v39 = 0;
      }
      catch ( ulong v54 )
      {
        if ( v54 != -2146435063 )
        {
          v45 = v54;
          throw &v45;
        }
        v63 = v57;
        Src = v51;
        v15 = v40;
        v17 = v53;
      }
      catch ( ... )
      {
        throw;
      }
      v40 = ++v15;
      String = NextString(v17);
      v14 = v58;
    }
    if ( !v37 )
    {
      v46 = -2146435026;
      throw &v46;
    }
    v29 = (unsigned int)v52 >> 2;
    *a5 = v29;
    ProcessHeap = GetProcessHeap();
    v31 = HeapAlloc(ProcessHeap, 8u, 4 * v29);
    *a4 = v31;
    if ( !v31 )
    {
      v47 = -2146435066;
      throw &v47;
    }
    v32 = Src;
    v33 = &Data;
    if ( HIDWORD(v52) )
      v33 = (const WCHAR *)Src;
    memcpy_0(v31, v33, 4LL * (unsigned int)*a5);
    if ( v59 )
    {
      v34 = v60;
      (**(void (__fastcall ***)(_DWORD *, _QWORD, _QWORD))v60)(v60, 0, 0);
      if ( *((LPVOID *)v34 + 7) == TlsGetValue(dwTlsIndex) && v34[16]-- == 1 )
      {
        *((_QWORD *)v34 + 7) = 0;
        if ( !SetEvent(*((HANDLE *)v34 + 9)) )
          GetLastError();
      }
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v34 + 8LL))(v34);
    }
  }
  catch ( ulong v55 )
  {
    v38 = v55;
    v32 = v51;
  }
  catch ( ... )
  {
    v38 = -2146435055;
    v32 = v51;
  }
  if ( v32 )
    operator delete[](v32);
  return v38;
}

```

## disassembly

```asm
0x180009da0  mov     r11, rsp
0x180009da3  mov     [r11+10h], rbx
0x180009da7  mov     [r11+18h], rsi
0x180009dab  mov     [r11+20h], r9
0x180009daf  mov     [r11+8], rcx
0x180009db3  push    rdi
0x180009db4  push    r12
0x180009db6  push    r13
0x180009db8  push    r14
0x180009dba  push    r15
0x180009dbc  sub     rsp, 0D0h
0x180009dc3  mov     ebx, r8d
0x180009dc6  mov     rdi, rdx
0x180009dc9  mov     r15, rcx
0x180009dcc  mov     [rsp+0F8h+var_58], rcx
0x180009dd4  xor     r14d, r14d
0x180009dd7  mov     [rsp+0F8h+var_C4], r14d
0x180009ddc  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180009de3  mov     [rsp+0F8h+var_88], rax
0x180009de8  mov     r13d, r14d
0x180009deb  mov     [rsp+0F8h+Src], r14
0x180009df0  mov     [r11-80h], r14
0x180009df4  mov     [r11-78h], r14
0x180009df8  mov     rdx, [rcx+48h]; lpTlsValue
0x180009dfc  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180009e02  call    cs:__imp_TlsSetValue
0x180009e08  test    eax, eax
0x180009e0a  jz      loc_18000A0FC
0x180009e10  mov     rdx, [r15]; lpTlsValue
0x180009e13  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x180009e19  call    cs:__imp_TlsSetValue
0x180009e1f  test    eax, eax
0x180009e21  jz      loc_18000A0FC
0x180009e27  mov     eax, 1
0x180009e2c  xchg    eax, cs:?g_fExtendShutdownTimer@@3JA; long g_fExtendShutdownTimer
0x180009e32  lea     rsi, [r15+50h]
0x180009e36  mov     [rsp+0F8h+var_40], rsi
0x180009e3e  mov     rcx, rsi; this
0x180009e41  call    ?Grab@CMutex@@QEAAXXZ; CMutex::Grab(void)
0x180009e46  mov     [rsp+0F8h+var_48], r15
0x180009e4e  test    rdi, rdi
0x180009e51  jnz     short loc_180009E6C
0x180009e53  mov     [rsp+0F8h+pExceptionObject], 80100011h
0x180009e5b  lea     rdx, _TI1K; pThrowInfo
0x180009e62  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180009e67  call    _CxxThrowException_0
0x180009e6c  shr     ebx, 1
0x180009e6e  cmp     ebx, 2
0x180009e71  jb      short loc_180009E53
0x180009e73  lea     eax, [rbx-1]
0x180009e76  cmp     r14w, [rdi+rax*2]
0x180009e7b  jnz     short loc_180009E53
0x180009e7d  lea     eax, [rbx-2]
0x180009e80  cmp     r14w, [rdi+rax*2]
0x180009e85  jnz     short loc_180009E53
0x180009e87  mov     ebx, r14d
0x180009e8a  mov     rcx, rdi; unsigned __int16 *
0x180009e8d  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x180009e92  test    rax, rax
0x180009e95  jz      short loc_180009EAF
0x180009e97  nop     word ptr [rax+rax+00000000h]
0x180009ea0  inc     ebx
0x180009ea2  mov     rcx, rax; unsigned __int16 *
0x180009ea5  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x180009eaa  test    rax, rax
0x180009ead  jnz     short loc_180009EA0
0x180009eaf  lea     ebx, ds:0[rbx*4]
0x180009eb6  test    ebx, ebx
0x180009eb8  jz      short loc_180009EDE
0x180009eba  mov     ecx, ebx; unsigned __int64
0x180009ebc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009ec1  mov     r13, rax
0x180009ec4  mov     [rsp+0F8h+Src], rax
0x180009ec9  test    rax, rax
0x180009ecc  jz      loc_18000A204
0x180009ed2  mov     [rsp+0F8h+var_80], rax
0x180009ed7  mov     [rsp+0F8h+var_74], ebx
0x180009ede  mov     [rsp+0F8h+var_78], ebx
0x180009ee5  mov     rbx, r13
0x180009ee8  mov     [rsp+0F8h+var_50], rbx
0x180009ef0  mov     [rsp+0F8h+var_C8], r14d
0x180009ef5  mov     r12d, r14d
0x180009ef8  mov     [rsp+0F8h+var_B8], r14d
0x180009efd  mov     rcx, rdi; unsigned __int16 *
0x180009f00  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x180009f05  mov     r15, rax
0x180009f08  mov     [rsp+0F8h+var_70], rax
0x180009f10  test    rax, rax
0x180009f13  jz      loc_18000A06F
0x180009f19  mov     ecx, r12d
0x180009f1c  lea     rax, [rbx+rcx*4]
0x180009f20  mov     [rsp+0F8h+var_60], rax
0x180009f28  mov     [rax], r14d
0x180009f2b  mov     [rsp+0F8h+var_C0], r14
0x180009f30  mov     rax, [rsp+0F8h+arg_0]
0x180009f38  mov     r13, [rax+0B0h]
0x180009f3f  mov     rbx, cs:?g_pcsControlLocks@@3PAPEAVCCriticalSectionObject@@A; CCriticalSectionObject * near * g_pcsControlLocks
0x180009f46  mov     [rsp+0F8h+var_38], rbx
0x180009f4e  mov     rax, [rbx]
0x180009f51  xor     r8d, r8d
0x180009f54  xor     edx, edx
0x180009f56  mov     rcx, rbx
0x180009f59  mov     rax, [rax]
0x180009f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f61  nop
0x180009f62  mov     eax, dword ptr cs:qword_18004B0C8+4
0x180009f68  mov     edi, eax
0x180009f6a  test    edi, edi
0x180009f6c  jz      loc_18000A0E2
0x180009f72  dec     edi
0x180009f74  cmp     eax, edi
0x180009f76  jbe     short loc_180009F6A
0x180009f78  lfence
0x180009f7b  movsxd  rcx, edi
0x180009f7e  mov     rax, cs:qword_18004B0D0
0x180009f85  mov     rsi, [rax+rcx*8]
0x180009f89  test    rsi, rsi
0x180009f8c  jz      short loc_180009FAC
0x180009f8e  cmp     dword ptr [rsi+1Ch], 0
0x180009f92  ja      loc_18000A094
0x180009f98  lea     rdx, Data; lpString2
0x180009f9f  mov     rcx, r15; lpString1
0x180009fa2  call    cs:__imp_lstrcmpiW
0x180009fa8  test    eax, eax
0x180009faa  jz      short loc_180009FB4
0x180009fac  mov     eax, dword ptr cs:qword_18004B0C8+4
0x180009fb2  jmp     short loc_180009F6A
0x180009fb4  mov     rax, [rsi]
0x180009fb7  mov     rcx, rsi
0x180009fba  mov     rax, [rax+38h]
0x180009fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fc3  test    rax, rax
0x180009fc6  jnz     loc_18000A09D
0x180009fcc  mov     ecx, 20h ; ' '; Size
0x180009fd1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009fd6  mov     rdi, rax
0x180009fd9  mov     [rsp+0F8h+var_30], rax
0x180009fe1  test    rax, rax
0x180009fe4  jz      loc_18000A21E
0x180009fea  xorps   xmm0, xmm0
0x180009fed  movups  xmmword ptr [rax+8], xmm0
0x180009ff1  mov     [rax+18h], r14d
0x180009ff5  mov     rcx, rsi; this
0x180009ff8  call    ?ReaderProxy@CReader@@QEAAPEAVCReaderProxy@@XZ; CReader::ReaderProxy(void)
0x180009ffd  mov     [rdi], rax
0x18000a000  test    rdi, rdi
0x18000a003  jz      loc_18000A226
0x18000a009  mov     rax, [rbx]
0x18000a00c  mov     rcx, rbx
0x18000a00f  mov     rax, [rax+8]
0x18000a013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a018  nop
0x18000a019  mov     [rsp+0F8h+var_C0], rdi
0x18000a01e  mov     rcx, [rdi]
0x18000a021  call    ?AvailabilityStatus@CReaderProxy@@QEAA?AW4AvailableState@CReader@@XZ; CReaderProxy::AvailabilityStatus(void)
0x18000a026  cmp     al, 9
0x18000a028  jnb     short loc_18000A03C
0x18000a02a  mov     rax, [rsp+0F8h+var_60]
0x18000a032  mov     dword ptr [rax], 1
0x18000a038  inc     [rsp+0F8h+var_C8]
0x18000a03c  mov     rcx, [rdi]; this
0x18000a03f  call    ?Release@CReaderProxy@@QEAAXXZ; CReaderProxy::Release(void)
0x18000a044  nop
0x18000a045  mov     rcx, rdi; Block
0x18000a048  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a04d  mov     [rsp+0F8h+var_C0], r14
0x18000a052  inc     r12d
0x18000a055  mov     [rsp+0F8h+var_B8], r12d
0x18000a05a  mov     rcx, r15; unsigned __int16 *
0x18000a05d  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x18000a062  mov     rbx, [rsp+0F8h+var_50]
0x18000a06a  jmp     loc_180009F05
0x18000a06f  cmp     [rsp+0F8h+var_C8], 0
0x18000a074  jnz     loc_18000A107
0x18000a07a  mov     [rsp+0F8h+var_A0], 8010002Eh
0x18000a082  lea     rdx, _TI1K; pThrowInfo
0x18000a089  lea     rcx, [rsp+0F8h+var_A0]; pExceptionObject
0x18000a08e  call    _CxxThrowException_0
0x18000a094  mov     rdx, [rsi+10h]
0x18000a098  jmp     loc_180009F9F
0x18000a09d  test    r13, r13
0x18000a0a0  jz      loc_180009FCC
0x18000a0a6  mov     rax, [rsi]
0x18000a0a9  mov     rcx, rsi
0x18000a0ac  mov     rax, [rax+38h]
0x18000a0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0b5  mov     rdx, r13; pSid2
0x18000a0b8  mov     rcx, rax; pSid1
0x18000a0bb  call    cs:__imp_EqualSid
0x18000a0c1  test    eax, eax
0x18000a0c3  jnz     loc_180009FCC
0x18000a0c9  mov     [rsp+0F8h+var_B0], 80100009h
0x18000a0d1  lea     rdx, _TI1K; pThrowInfo
0x18000a0d8  lea     rcx, [rsp+0F8h+var_B0]; pExceptionObject
0x18000a0dd  call    _CxxThrowException_0
0x18000a0e2  mov     [rsp+0F8h+var_A8], 80100009h
0x18000a0ea  lea     rdx, _TI1K; pThrowInfo
0x18000a0f1  lea     rcx, [rsp+0F8h+var_A8]; pExceptionObject
0x18000a0f6  call    _CxxThrowException_0
0x18000a0fc  call    cs:__imp_GetLastError
0x18000a102  jmp     loc_180009E27
0x18000a107  mov     ebx, [rsp+0F8h+var_78]
0x18000a10e  shr     ebx, 2
0x18000a111  mov     rdi, [rsp+0F8h+arg_20]
0x18000a119  mov     [rdi], ebx
0x18000a11b  shl     rbx, 2
0x18000a11f  call    cs:__imp_GetProcessHeap
0x18000a125  mov     rcx, rax; hHeap
0x18000a128  mov     r8, rbx; dwBytes
0x18000a12b  mov     edx, 8; dwFlags
0x18000a130  call    cs:__imp_HeapAlloc
0x18000a136  mov     rcx, [rsp+0F8h+arg_18]
0x18000a13e  mov     [rcx], rax
0x18000a141  test    rax, rax
0x18000a144  jz      loc_18000A27C
0x18000a14a  cmp     [rsp+0F8h+var_74], 0
0x18000a152  mov     r13, [rsp+0F8h+Src]
0x18000a157  lea     rdx, Data
0x18000a15e  cmova   rdx, r13; Src
0x18000a162  mov     r8d, [rdi]
0x18000a165  shl     r8, 2; Size
0x18000a169  mov     rcx, rax; void *
0x18000a16c  call    memcpy_0
0x18000a171  nop
0x18000a172  cmp     [rsp+0F8h+var_48], 0
0x18000a17b  jz      short loc_18000A1D6
0x18000a17d  mov     rsi, [rsp+0F8h+var_40]
0x18000a185  mov     rax, [rsi]
0x18000a188  xor     r8d, r8d
0x18000a18b  xor     edx, edx
0x18000a18d  mov     rcx, rsi
0x18000a190  mov     rax, [rax]
0x18000a193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a198  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000a19e  call    cs:__imp_TlsGetValue
0x18000a1a4  cmp     [rsi+38h], rax
0x18000a1a8  jnz     short loc_18000A1C6
0x18000a1aa  add     dword ptr [rsi+40h], 0FFFFFFFFh
0x18000a1ae  jnz     short loc_18000A1C6
0x18000a1b0  mov     [rsi+38h], r14
0x18000a1b4  mov     rcx, [rsi+48h]; hEvent
0x18000a1b8  call    cs:__imp_SetEvent
0x18000a1be  test    eax, eax
0x18000a1c0  jz      loc_18000A296
0x18000a1c6  mov     rax, [rsi]
0x18000a1c9  mov     rcx, rsi
0x18000a1cc  mov     rax, [rax+8]
0x18000a1d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1d5  nop
0x18000a1d6  test    r13, r13
0x18000a1d9  jz      short loc_18000A1E3
0x18000a1db  mov     rcx, r13; Block
0x18000a1de  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000a1e3  mov     eax, [rsp+0F8h+var_C4]
0x18000a1e7  lea     r11, [rsp+0F8h+var_28]
0x18000a1ef  mov     rbx, [r11+38h]
0x18000a1f3  mov     rsi, [r11+40h]
0x18000a1f7  mov     rsp, r11
0x18000a1fa  pop     r15
0x18000a1fc  pop     r14
0x18000a1fe  pop     r13
0x18000a200  pop     r12
0x18000a202  pop     rdi
0x18000a203  retn
0x18000a204  mov     [rsp+0F8h+var_B4], 0Eh
0x18000a20c  lea     rdx, _TI1K; pThrowInfo
0x18000a213  lea     rcx, [rsp+0F8h+var_B4]; pExceptionObject
0x18000a218  call    _CxxThrowException_0
0x18000a21e  mov     rdi, r14
0x18000a221  jmp     loc_18000A000
0x18000a226  xor     r8d, r8d; unsigned __int16 *
0x18000a229  mov     edx, 0CBh; unsigned int
0x18000a22e  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x18000a233  mov     [rsp+0F8h+var_AC], 80100006h
0x18000a23b  lea     rdx, _TI1K; pThrowInfo
0x18000a242  lea     rcx, [rsp+0F8h+var_AC]; pExceptionObject
0x18000a247  call    _CxxThrowException_0
0x18000a24d  xor     r14d, r14d
0x18000a250  mov     rax, [rsp+0F8h+var_58]
0x18000a258  mov     [rsp+0F8h+arg_0], rax
0x18000a260  mov     rax, [rsp+0F8h+var_80]
0x18000a265  mov     [rsp+0F8h+Src], rax
0x18000a26a  mov     r12d, [rsp+0F8h+var_B8]
0x18000a26f  mov     r15, [rsp+0F8h+var_70]
0x18000a277  jmp     loc_18000A052
0x18000a27c  mov     [rsp+0F8h+var_9C], 80100006h
0x18000a284  lea     rdx, _TI1K; pThrowInfo
0x18000a28b  lea     rcx, [rsp+0F8h+var_9C]; pExceptionObject
0x18000a290  call    _CxxThrowException_0
0x18000a296  call    cs:__imp_GetLastError
0x18000a29c  jmp     loc_18000A1C6
0x18000a2a1  jmp     short $+2
0x18000a2a3  mov     r13, [rsp+0F8h+var_80]
0x18000a2a8  jmp     loc_18000A1D6
```
