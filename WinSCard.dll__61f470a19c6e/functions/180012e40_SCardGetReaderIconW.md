# SCardGetReaderIconW

- ea: `0x180012e40`
- end: `0x180012f76`
- name: `SCardGetReaderIconW`
- size: `310`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int16 *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180002a30`
- `0x1800093e4`
- `0x180010898`
- `0x1800126f0`
- `0x180012e40`
- `0x1800190cc`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012e71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012e71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012ea7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012ea7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SCardGetReaderIconW(
        unsigned __int64 a1,
        unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned int v8; // edi
  CHandleList *v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // rsi
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v12; // rbx
  ulong v13; // eax
  ulong ReaderIcon; // eax
  ulong pExceptionObject; // [rsp+28h] [rbp-50h] BYREF
  ulong v20; // [rsp+2Ch] [rbp-4Ch] BYREF
  ulong v21; // [rsp+30h] [rbp-48h] BYREF
  ulong v22; // [rsp+34h] [rbp-44h] BYREF
  ulong v23; // [rsp+38h] [rbp-40h] BYREF
  ulong v24; // [rsp+3Ch] [rbp-3Ch] BYREF

  v8 = 0;
  try
  {
    v9 = g_phlContexts;
    v10 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    HandlePtr = CHandleList::GetHandlePtr(v9, a1);
    if ( !HandlePtr )
    {
      pExceptionObject = 6;
      throw &pExceptionObject;
    }
    v12 = *(_QWORD *)HandlePtr;
    LeaveCriticalSection(v10);
    if ( *(_DWORD *)(v12 + 16) )
    {
      v20 = -2146435042;
      throw &v20;
    }
    if ( *(_QWORD *)(v12 + 128) || !RedirectionContextIsLocal(0) )
    {
      if ( RedirectDisabled() )
      {
        v22 = -2146435043;
        throw &v22;
      }
      ReaderIcon = RedirectedSCardGetReaderIcon(*(struct _REDIR_LOCAL_SCARDCONTEXT **)(v12 + 128), a2, a3, a4);
      if ( ReaderIcon )
      {
        v23 = ReaderIcon;
        throw &v23;
      }
    }
    else
    {
      v13 = GetReaderIcon((struct CSCardUserContext *)v12, a2, a3, a4);
      if ( v13 )
      {
        v21 = v13;
        throw &v21;
      }
    }
  }
  catch ( ulong v24 )
  {
    return v24;
  }
  catch ( ... )
  {
    return (unsigned int)-2146435068;
  }
  return v8;
}

```

## disassembly

```asm
0x180012e40  push    rbx
0x180012e42  push    rsi
0x180012e43  push    rdi
0x180012e44  push    r12
0x180012e46  push    r13
0x180012e48  push    r14
0x180012e4a  push    r15
0x180012e4c  sub     rsp, 40h
0x180012e50  mov     r15, r9
0x180012e53  mov     r12, r8
0x180012e56  mov     r13, rdx
0x180012e59  mov     r14, rcx
0x180012e5c  xor     edi, edi
0x180012e5e  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x180012e65  lea     rsi, [rbx+20h]
0x180012e69  mov     [rsp+78h+var_58], rsi
0x180012e6e  mov     rcx, rsi; lpCriticalSection
0x180012e71  call    cs:__imp_EnterCriticalSection
0x180012e77  nop
0x180012e78  mov     rdx, r14; unsigned __int64
0x180012e7b  mov     rcx, rbx; this
0x180012e7e  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x180012e83  test    rax, rax
0x180012e86  jnz     short loc_180012EA1
0x180012e88  mov     [rsp+78h+pExceptionObject], 6
0x180012e90  lea     rdx, _TI1K; pThrowInfo
0x180012e97  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180012e9c  call    _CxxThrowException_0
0x180012ea1  mov     rbx, [rax]
0x180012ea4  mov     rcx, rsi; lpCriticalSection
0x180012ea7  call    cs:__imp_LeaveCriticalSection
0x180012ead  cmp     dword ptr [rbx+10h], 0
0x180012eb1  jz      short loc_180012ECC
0x180012eb3  mov     [rsp+78h+var_4C], 8010001Eh
0x180012ebb  lea     rdx, _TI1K; pThrowInfo
0x180012ec2  lea     rcx, [rsp+78h+var_4C]; pExceptionObject
0x180012ec7  call    _CxxThrowException_0
0x180012ecc  cmp     qword ptr [rbx+80h], 0
0x180012ed4  jnz     short loc_180012F0B
0x180012ed6  xor     ecx, ecx; lpCriticalSection
0x180012ed8  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x180012edd  test    al, al
0x180012edf  jz      short loc_180012F0B
0x180012ee1  mov     r9, r15; unsigned int *
0x180012ee4  mov     r8, r12; unsigned __int8 *
0x180012ee7  mov     rdx, r13; unsigned __int16 *
0x180012eea  mov     rcx, rbx; struct CSCardUserContext *
0x180012eed  call    ?GetReaderIcon@@YAJPEAVCSCardUserContext@@PEBGPEAEPEAK@Z; GetReaderIcon(CSCardUserContext *,ushort const *,uchar *,ulong *)
0x180012ef2  test    eax, eax
0x180012ef4  jz      short loc_180012F5C
0x180012ef6  mov     [rsp+78h+var_48], eax
0x180012efa  lea     rdx, _TI1K; pThrowInfo
0x180012f01  lea     rcx, [rsp+78h+var_48]; pExceptionObject
0x180012f06  call    _CxxThrowException_0
0x180012f0b  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x180012f10  test    al, al
0x180012f12  jz      short loc_180012F2D
0x180012f14  mov     [rsp+78h+var_44], 8010001Dh
0x180012f1c  lea     rdx, _TI1K; pThrowInfo
0x180012f23  lea     rcx, [rsp+78h+var_44]; pExceptionObject
0x180012f28  call    _CxxThrowException_0
0x180012f2d  mov     r9, r15; unsigned int *
0x180012f30  mov     r8, r12; unsigned __int8 *
0x180012f33  mov     rdx, r13; unsigned __int16 *
0x180012f36  mov     rcx, [rbx+80h]; struct _REDIR_LOCAL_SCARDCONTEXT *
0x180012f3d  call    ?RedirectedSCardGetReaderIcon@@YAJ_KPEBGPEAEPEAK@Z; RedirectedSCardGetReaderIcon(unsigned __int64,ushort const *,uchar *,ulong *)
0x180012f42  test    eax, eax
0x180012f44  jz      short loc_180012F5C
0x180012f46  mov     [rsp+78h+var_40], eax
0x180012f4a  lea     rdx, _TI1K; pThrowInfo
0x180012f51  lea     rcx, [rsp+78h+var_40]; pExceptionObject
0x180012f56  call    _CxxThrowException_0
0x180012f5c  jmp     short loc_180012F64
0x180012f5e  jmp     short $+2
0x180012f60  mov     edi, dword ptr [rsp+78h+var_58]
0x180012f64  mov     eax, edi
0x180012f66  add     rsp, 40h
0x180012f6a  pop     r15
0x180012f6c  pop     r14
0x180012f6e  pop     r13
0x180012f70  pop     r12
0x180012f72  pop     rdi
0x180012f73  pop     rsi
0x180012f74  pop     rbx
0x180012f75  retn
```
