# CHandlerInfo::ExecuteAction(SYNCMGR_HANDLERACTIONS,CSyncMgrID const &,HWND__ *,bool,SYNCMGR_CONTROL_FLAGS,void *,long *)

- ea: `0x180016d08`
- end: `0x180016eb2`
- name: `?ExecuteAction@CHandlerInfo@@QEAAJW4SYNCMGR_HANDLERACTIONS@@AEBVCSyncMgrID@@PEAUHWND__@@_NW4SYNCMGR_CONTROL_FLAGS@@PEAXPEAJ@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180013bb8`

## callees

- `0x180005660`
- `0x1800074a4`
- `0x180009940`
- `0x18000a5e4`
- `0x18000a714`
- `0x180016d08`
- `0x180019268`
- `0x18001c368`
- `0x18005292a`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x180016e81`
- `SHLWAPI!__imp_SHCreateThread` at `0x180016e81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016daa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016daa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016d56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016d56`

## pseudocode

```c
__int64 __fastcall CHandlerInfo::ExecuteAction(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        char a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  int ItemInfo; // edi
  void *v13; // rax
  void *v14; // r14
  char v15; // bp
  const WCHAR *v16; // r12
  int v17; // eax
  char v19; // bl
  __int64 v20; // rcx
  __int32 v21; // r10d
  struct CSyncItemInfo *v22; // [rsp+20h] [rbp-58h] BYREF

  ItemInfo = -2147024882;
  v13 = operator new(0xB0u);
  v14 = v13;
  if ( v13 )
  {
    memset_0(v13, 0, 0xB0u);
    v15 = 1;
    EnterCriticalSection(*(LPCRITICAL_SECTION *)(a1 + 8));
    v16 = (const WCHAR *)(a3 + 144);
    LOBYTE(a3) = 0;
    if ( *v16 )
    {
      v22 = 0;
      ItemInfo = CHandlerInfo::_FindItemInfo((CHandlerInfo *)a1, v16, &v22);
      if ( ItemInfo < 0 )
      {
        v15 = 0;
      }
      else
      {
        LODWORD(a3) = *((_DWORD *)v22 + 212);
        CItemInfo::Release(v22);
      }
    }
    else
    {
      LODWORD(a3) = *(_DWORD *)(a1 + 888);
    }
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)(a1 + 8));
    v17 = 0;
    if ( v15 != 1 )
      v17 = ItemInfo;
    ItemInfo = v17;
    if ( v17 >= 0 )
    {
      switch ( a2 )
      {
        case 5:
          if ( (a3 & 0x10) == 0 )
            return (unsigned int)-2147024891;
          goto LABEL_21;
        case 6:
          v19 = a3 & 0x20;
          break;
        case 7:
          v19 = a3 & 0x40;
          break;
        default:
          if ( a2 == 8 && (a3 & 0x80u) == 0LL )
            return (unsigned int)-2147024891;
LABEL_21:
          if ( v15 )
          {
            *((_DWORD *)v14 + 11) = a6;
            *((_QWORD *)v14 + 3) = a7;
            *((_QWORD *)v14 + 4) = a8;
            *((_BYTE *)v14 + 16) = a5;
            *((_QWORD *)v14 + 1) = a4;
            *((_DWORD *)v14 + 10) = a2;
            *(_QWORD *)v14 = a1;
            StringCchCopyW((unsigned __int16 *)v14 + 24, 0x40u, v16);
            _InterlockedIncrement((volatile signed __int32 *)(a1 + 2076));
            v20 = *(_QWORD *)(a1 + 16);
            _InterlockedExchange((volatile __int32 *)(v20 + 96), v21);
            _InterlockedIncrement((volatile signed __int32 *)(v20 + 396));
            if ( SHCreateThread(CHandlerInfo::s_ActionThreadProc, v14, 0, 0) )
            {
              return 0;
            }
            else
            {
              CZeroInitNew::operator delete(v14);
              CHandlerInfo::Release((CHandlerInfo *)a1);
              CHandlerCache::Release(*(CHandlerCache **)(a1 + 16));
            }
            return (unsigned int)ItemInfo;
          }
          return (unsigned int)-2147024891;
      }
      v15 = v19 != 0 ? v15 : 0;
      goto LABEL_21;
    }
  }
  return (unsigned int)ItemInfo;
}

```

## disassembly

```asm
0x180016d08  push    rbx
0x180016d0a  push    rbp
0x180016d0b  push    rsi
0x180016d0c  push    rdi
0x180016d0d  push    r12
0x180016d0f  push    r13
0x180016d11  push    r14
0x180016d13  push    r15
0x180016d15  sub     rsp, 38h
0x180016d19  mov     rsi, rcx
0x180016d1c  mov     ebp, 0B0h
0x180016d21  mov     ecx, ebp; unsigned __int64
0x180016d23  mov     r13, r9
0x180016d26  mov     rbx, r8
0x180016d29  mov     r15d, edx
0x180016d2c  mov     edi, 8007000Eh
0x180016d31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016d36  mov     r14, rax
0x180016d39  test    rax, rax
0x180016d3c  jz      loc_180016DE7
0x180016d42  mov     r8d, ebp; Size
0x180016d45  xor     edx, edx; Val
0x180016d47  mov     rcx, rax; void *
0x180016d4a  call    memset_0
0x180016d4f  mov     rcx, [rsi+8]; lpCriticalSection
0x180016d53  mov     bpl, 1
0x180016d56  call    cs:__imp_EnterCriticalSection
0x180016d5c  lea     r12, [rbx+90h]
0x180016d63  xor     ebx, ebx
0x180016d65  cmp     [r12], bx
0x180016d6a  jnz     short loc_180016D74
0x180016d6c  mov     ebx, [rsi+378h]
0x180016d72  jmp     short loc_180016DA6
0x180016d74  lea     r8, [rsp+78h+var_58]; struct CSyncItemInfo **
0x180016d79  mov     [rsp+78h+var_58], rbx
0x180016d7e  mov     rdx, r12; unsigned __int16 *
0x180016d81  mov     rcx, rsi; this
0x180016d84  call    ?_FindItemInfo@CHandlerInfo@@AEBAJQEBGPEAPEAVCSyncItemInfo@@@Z; CHandlerInfo::_FindItemInfo(ushort const * const,CSyncItemInfo * *)
0x180016d89  mov     edi, eax
0x180016d8b  test    eax, eax
0x180016d8d  js      short loc_180016DA1
0x180016d8f  mov     rcx, [rsp+78h+var_58]; this
0x180016d94  mov     ebx, [rcx+350h]
0x180016d9a  call    ?Release@CItemInfo@@QEAAKXZ; CItemInfo::Release(void)
0x180016d9f  jmp     short loc_180016DA6
0x180016da1  xor     ecx, ecx
0x180016da3  mov     bpl, cl
0x180016da6  mov     rcx, [rsi+8]; lpCriticalSection
0x180016daa  call    cs:__imp_LeaveCriticalSection
0x180016db0  xor     r10d, r10d
0x180016db3  cmp     bpl, 1
0x180016db7  mov     eax, r10d
0x180016dba  cmovnz  eax, edi
0x180016dbd  mov     edi, eax
0x180016dbf  test    eax, eax
0x180016dc1  js      short loc_180016DE7
0x180016dc3  mov     ecx, r15d
0x180016dc6  lea     edx, [r10+40h]; unsigned __int64
0x180016dca  sub     ecx, 5
0x180016dcd  jz      short loc_180016E0A
0x180016dcf  sub     ecx, 1
0x180016dd2  jz      short loc_180016DFE
0x180016dd4  sub     ecx, 1
0x180016dd7  jz      short loc_180016DFA
0x180016dd9  cmp     ecx, 1
0x180016ddc  jnz     short loc_180016E0F
0x180016dde  test    bl, bl
0x180016de0  js      short loc_180016E0F
0x180016de2  mov     edi, 80070005h
0x180016de7  mov     eax, edi
0x180016de9  add     rsp, 38h
0x180016ded  pop     r15
0x180016def  pop     r14
0x180016df1  pop     r13
0x180016df3  pop     r12
0x180016df5  pop     rdi
0x180016df6  pop     rsi
0x180016df7  pop     rbp
0x180016df8  pop     rbx
0x180016df9  retn
0x180016dfa  and     bl, dl
0x180016dfc  jmp     short loc_180016E01
0x180016dfe  and     bl, 20h
0x180016e01  neg     bl
0x180016e03  sbb     al, al
0x180016e05  and     bpl, al
0x180016e08  jmp     short loc_180016E0F
0x180016e0a  test    bl, 10h
0x180016e0d  jz      short loc_180016DE2
0x180016e0f  test    bpl, bpl
0x180016e12  jz      short loc_180016DE2
0x180016e14  mov     eax, [rsp+78h+arg_28]
0x180016e1b  lea     rcx, [r14+30h]; unsigned __int16 *
0x180016e1f  mov     [r14+2Ch], eax
0x180016e23  mov     r8, r12; unsigned __int16 *
0x180016e26  mov     rax, [rsp+78h+arg_30]
0x180016e2e  mov     [r14+18h], rax
0x180016e32  mov     rax, [rsp+78h+arg_38]
0x180016e3a  mov     [r14+20h], rax
0x180016e3e  mov     al, [rsp+78h+arg_20]
0x180016e45  mov     [r14+10h], al
0x180016e49  mov     [r14+8], r13
0x180016e4d  mov     [r14+28h], r15d
0x180016e51  mov     [r14], rsi
0x180016e54  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016e59  lock inc dword ptr [rsi+81Ch]
0x180016e60  mov     rcx, [rsi+10h]
0x180016e64  mov     eax, r10d
0x180016e67  xchg    eax, [rcx+60h]
0x180016e6a  lock inc dword ptr [rcx+18Ch]
0x180016e71  xor     r9d, r9d; pfnCallback
0x180016e74  lea     rcx, ?s_ActionThreadProc@CHandlerInfo@@CAKPEAX@Z; pfnThreadProc
0x180016e7b  xor     r8d, r8d; flags
0x180016e7e  mov     rdx, r14; pData
0x180016e81  call    cs:__imp_SHCreateThread
0x180016e87  xor     ecx, ecx
0x180016e89  test    eax, eax
0x180016e8b  jz      short loc_180016E94
0x180016e8d  mov     edi, ecx
0x180016e8f  jmp     loc_180016DE7
0x180016e94  mov     rcx, r14; lpMem
0x180016e97  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x180016e9c  mov     rcx, rsi; this
0x180016e9f  call    ?Release@CHandlerInfo@@QEAAKXZ; CHandlerInfo::Release(void)
0x180016ea4  mov     rcx, [rsi+10h]; this
0x180016ea8  call    ?Release@CHandlerCache@@QEAAJXZ; CHandlerCache::Release(void)
0x180016ead  jmp     loc_180016DE7
```
