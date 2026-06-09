# CGrepRowsetEvents::CNotificationThread::_InitThread(uint,CGrepRowsetEvents::SCOPE_REGISTRATION const *)

- ea: `0x180044cd0`
- end: `0x180044e45`
- name: `?_InitThread@CNotificationThread@CGrepRowsetEvents@@AEAAJIPEBUSCOPE_REGISTRATION@2@@Z`
- size: `373`
- prototype: `__int64 __fastcall(CGrepRowsetEvents::CNotificationThread *__hidden this, unsigned int, const struct CGrepRowsetEvents::SCOPE_REGISTRATION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008efe0`

## callees

- `0x180044cd0`
- `0x180044e4c`
- `0x18006c6bc`

## import_xrefs

- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x180044d35`
- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x180044d35`
- `Windows.Storage!SHParseDisplayName` at `0x180044d10`
- `Windows.Storage!SHParseDisplayName` at `0x180044d10`
- `Windows.Storage!ILIsEqual` at `0x180044d90`
- `Windows.Storage!ILIsEqual` at `0x180044d90`
- `Windows.Storage!__imp_SHChangeNotifyRegister` at `0x180044dc8`
- `Windows.Storage!__imp_SHChangeNotifyRegister` at `0x180044dc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044e24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044e24`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CGrepRowsetEvents::CNotificationThread::_InitThread(
        CGrepRowsetEvents::CNotificationThread *this,
        unsigned int a2,
        const struct CGrepRowsetEvents::SCOPE_REGISTRATION *a3)
{
  __int64 v6; // rax
  int Error; // ebx
  unsigned int v8; // esi
  const ITEMIDLIST *v9; // rdx
  int v10; // edi
  BOOL v11; // eax
  LONG v12; // r8d
  ULONG v13; // ebp
  __int64 v14; // rdx
  ULONG *v15; // rdx
  ITEMIDLIST *v16; // rcx
  SHChangeNotifyEntry pshcne; // [rsp+30h] [rbp-38h] BYREF
  LPCITEMIDLIST pidl1; // [rsp+70h] [rbp+8h] BYREF

  pidl1 = 0;
  SHParseDisplayName(L"shell:::{a6482830-08eb-41e2-84c1-73920c2badb9}", 0, (LPITEMIDLIST *)&pidl1, 0, 0);
  v6 = SHCreateWorkerWindowW(CGrepRowsetEvents::CNotificationThread::s_WndProc, -3, 0);
  *((_QWORD *)this + 11) = v6;
  if ( v6 )
  {
    Error = 0;
    v8 = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    v8 = 0;
    if ( Error < 0 )
      goto LABEL_14;
  }
  do
  {
    if ( v8 >= a2 )
      break;
    v9 = (const ITEMIDLIST *)*((_QWORD *)a3 + 2 * v8);
    pshcne.pidl = v9;
    pshcne.fRecursive = *((unsigned __int8 *)a3 + 16 * v8 + 8);
    v10 = pshcne.fRecursive ? 0x1000 : 0;
    if ( pidl1 )
    {
      v11 = ILIsEqual(pidl1, v9);
      v12 = 145919;
      if ( v11 )
        continue;
    }
    v12 = 145439;
    v13 = SHChangeNotifyRegister(*((HWND *)this + 11), v10 + 32771, v12, 0x401u, 1, &pshcne);
    if ( v13 )
    {
      Error = 0;
      v14 = *((_QWORD *)this + 8);
      if ( v14 != *((_QWORD *)this + 10)
        || (Error = CTSimpleArray<unsigned long,4294967294,CTPolicyCoTaskMem<unsigned long>,CSimpleArrayStandardCompareHelper<unsigned long>,CSimpleArrayStandardMergeHelper<unsigned long>>::_EnsureCapacity(
                      (char *)this + 56,
                      v14 + 1),
            Error >= 0) )
      {
        v15 = (ULONG *)(*((_QWORD *)this + 7) + 4 * (*((_QWORD *)this + 8))++);
        if ( v15 )
          *v15 = v13;
      }
    }
    ++v8;
  }
  while ( Error >= 0 );
LABEL_14:
  v16 = (ITEMIDLIST *)pidl1;
  pidl1 = 0;
  CoTaskMemFree(v16);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180044cd0  mov     rax, rsp
0x180044cd3  mov     [rax+10h], rbx
0x180044cd7  mov     [rax+18h], rbp
0x180044cdb  push    rsi
0x180044cdc  push    rdi
0x180044cdd  push    r12
0x180044cdf  push    r14
0x180044ce1  push    r15
0x180044ce3  sub     rsp, 40h
0x180044ce7  mov     r15, r8
0x180044cea  mov     r12d, edx
0x180044ced  mov     r14, rcx
0x180044cf0  mov     qword ptr [rax+8], 0
0x180044cf8  mov     qword ptr [rax-48h], 0
0x180044d00  xor     r9d, r9d; sfgaoIn
0x180044d03  lea     r8, [rax+8]; ppidl
0x180044d07  xor     edx, edx; pbc
0x180044d09  lea     rcx, aShellA64828300; "shell:::{a6482830-08eb-41e2-84c1-73920c"...
0x180044d10  call    cs:__imp_SHParseDisplayName
0x180044d16  mov     [rsp+68h+pshcne], r14
0x180044d1b  mov     qword ptr [rsp+68h+cEntries], 0
0x180044d24  xor     r9d, r9d
0x180044d27  xor     r8d, r8d
0x180044d2a  lea     rdx, [r9-3]
0x180044d2e  lea     rcx, ?s_WndProc@CNotificationThread@CGrepRowsetEvents@@CA_JPEAUHWND__@@I_K_J@Z; CGrepRowsetEvents::CNotificationThread::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180044d35  call    cs:__imp_SHCreateWorkerWindowW
0x180044d3b  mov     [r14+58h], rax
0x180044d3f  test    rax, rax
0x180044d42  jz      short loc_180044D4A
0x180044d44  xor     ebx, ebx
0x180044d46  xor     esi, esi
0x180044d48  jmp     short loc_180044D5B
0x180044d4a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180044d4f  mov     ebx, eax
0x180044d51  xor     esi, esi
0x180044d53  test    eax, eax
0x180044d55  js      loc_180044E16
0x180044d5b  cmp     esi, r12d
0x180044d5e  jnb     loc_180044E16
0x180044d64  mov     eax, esi
0x180044d66  add     rax, rax
0x180044d69  mov     rdx, [r15+rax*8]; pidl2
0x180044d6d  mov     [rsp+68h+var_38.pidl], rdx
0x180044d72  movzx   eax, byte ptr [r15+rax*8+8]
0x180044d78  mov     [rsp+68h+var_38.fRecursive], eax
0x180044d7c  neg     eax
0x180044d7e  sbb     edi, edi
0x180044d80  and     edi, 1000h
0x180044d86  mov     rcx, [rsp+68h+pidl1]; pidl1
0x180044d8b  test    rcx, rcx
0x180044d8e  jz      short loc_180044DA0
0x180044d90  call    cs:__imp_ILIsEqual
0x180044d96  test    eax, eax
0x180044d98  mov     r8d, 239FFh
0x180044d9e  jnz     short loc_180044DA6
0x180044da0  mov     r8d, 2381Fh; fEvents
0x180044da6  lea     rax, [rsp+68h+var_38]
0x180044dab  mov     [rsp+68h+pshcne], rax; pshcne
0x180044db0  mov     [rsp+68h+cEntries], 1; cEntries
0x180044db8  mov     r9d, 401h; wMsg
0x180044dbe  lea     edx, [rdi+8003h]; fSources
0x180044dc4  mov     rcx, [r14+58h]; hwnd
0x180044dc8  call    cs:__imp_SHChangeNotifyRegister
0x180044dce  mov     ebp, eax
0x180044dd0  test    eax, eax
0x180044dd2  jz      short loc_180044E0C
0x180044dd4  xor     ebx, ebx
0x180044dd6  mov     rdx, [r14+40h]
0x180044dda  cmp     rdx, [r14+50h]
0x180044dde  jnz     short loc_180044DF2
0x180044de0  inc     rdx
0x180044de3  lea     rcx, [r14+38h]
0x180044de7  call    ?_EnsureCapacity@?$CTSimpleArray@K$0PPPPPPPO@V?$CTPolicyCoTaskMem@K@@V?$CSimpleArrayStandardCompareHelper@K@@V?$CSimpleArrayStandardMergeHelper@K@@@@QEAAJ_K0@Z; CTSimpleArray<ulong,4294967294,CTPolicyCoTaskMem<ulong>,CSimpleArrayStandardCompareHelper<ulong>,CSimpleArrayStandardMergeHelper<ulong>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180044dec  mov     ebx, eax
0x180044dee  test    eax, eax
0x180044df0  js      short loc_180044E0C
0x180044df2  inc     qword ptr [r14+40h]
0x180044df6  mov     rdx, [r14+40h]
0x180044dfa  mov     rax, [r14+38h]
0x180044dfe  dec     rdx
0x180044e01  lea     rdx, [rax+rdx*4]
0x180044e05  test    rdx, rdx
0x180044e08  jz      short loc_180044E0C
0x180044e0a  mov     [rdx], ebp
0x180044e0c  inc     esi
0x180044e0e  test    ebx, ebx
0x180044e10  jns     loc_180044D5B
0x180044e16  mov     rcx, [rsp+68h+pidl1]; pv
0x180044e1b  mov     [rsp+68h+pidl1], 0
0x180044e24  call    cs:__imp_CoTaskMemFree
0x180044e2a  mov     eax, ebx
0x180044e2c  lea     r11, [rsp+68h+var_28]
0x180044e31  mov     rbx, [r11+38h]
0x180044e35  mov     rbp, [r11+40h]
0x180044e39  mov     rsp, r11
0x180044e3c  pop     r15
0x180044e3e  pop     r14
0x180044e40  pop     r12
0x180044e42  pop     rdi
0x180044e43  pop     rsi
0x180044e44  retn
```
