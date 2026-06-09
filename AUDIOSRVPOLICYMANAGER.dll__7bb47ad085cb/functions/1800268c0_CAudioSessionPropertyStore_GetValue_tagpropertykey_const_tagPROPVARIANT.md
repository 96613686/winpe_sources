# CAudioSessionPropertyStore::GetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x1800268c0`
- end: `0x180026999`
- name: `?GetValue@CAudioSessionPropertyStore@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(CAudioSessionPropertyStore *this, const struct _tagpropertykey *, PROPVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a384`
- `0x1800268c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026910`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026910`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026976`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026988`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026976`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026988`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180026949`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180026949`

## pseudocode

```c
__int64 __fastcall CAudioSessionPropertyStore::GetValue(
        CAudioSessionPropertyStore *this,
        const struct _tagpropertykey *a2,
        PROPVARIANT *a3)
{
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  __int64 i; // rdx
  __int64 v9; // rax
  HRESULT v10; // eax
  unsigned int v11; // edi
  int v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a3 )
  {
    v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
    *(_OWORD *)a3 = 0;
    a3[2] = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    for ( i = *((_QWORD *)this + 4); i; i = *(_QWORD *)(i + 48) )
    {
      if ( *(_DWORD *)(i + 16) == a2->pid )
      {
        v9 = *(_QWORD *)i - *(_QWORD *)&a2->fmtid.Data1;
        if ( *(_QWORD *)i == *(_QWORD *)&a2->fmtid.Data1 )
          v9 = *(_QWORD *)(i + 8) - *(_QWORD *)a2->fmtid.Data4;
        if ( !v9 )
        {
          v10 = PropVariantCopy(a3, (const PROPVARIANT *)(i + 24));
          v11 = v10;
          if ( v10 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1D1,
              (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
              (const char *)(unsigned int)v10,
              v12);
            if ( v7 )
              LeaveCriticalSection(v7);
            return v11;
          }
          break;
        }
      }
    }
    if ( v7 )
      LeaveCriticalSection(v7);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C5,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
      (const char *)0x80004003LL,
      v12);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800268c0  push    rbx
0x1800268c2  push    rbp
0x1800268c3  push    rsi
0x1800268c4  push    rdi
0x1800268c5  sub     rsp, 28h
0x1800268c9  mov     rdi, r8
0x1800268cc  mov     rsi, rdx
0x1800268cf  mov     rbp, rcx
0x1800268d2  test    r8, r8
0x1800268d5  jnz     short loc_1800268FC
0x1800268d7  mov     rcx, [rsp+48h]; this
0x1800268dc  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x1800268e3  mov     ebx, 80004003h
0x1800268e8  mov     edx, 1C5h; void *
0x1800268ed  mov     r9d, ebx; char *
0x1800268f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800268f5  mov     eax, ebx
0x1800268f7  jmp     loc_180026990
0x1800268fc  xorps   xmm0, xmm0
0x1800268ff  lea     rbx, [rcx+30h]
0x180026903  xor     eax, eax
0x180026905  mov     rcx, rbx; lpCriticalSection
0x180026908  movups  xmmword ptr [r8], xmm0
0x18002690c  mov     [r8+10h], rax
0x180026910  call    cs:__imp_EnterCriticalSection
0x180026916  mov     rdx, [rbp+20h]
0x18002691a  test    rdx, rdx
0x18002691d  jz      short loc_180026980
0x18002691f  mov     eax, [rsi+10h]
0x180026922  cmp     [rdx+10h], eax
0x180026925  jnz     short loc_18002693C
0x180026927  mov     rax, [rdx]
0x18002692a  sub     rax, [rsi]
0x18002692d  jnz     short loc_180026937
0x18002692f  mov     rax, [rdx+8]
0x180026933  sub     rax, [rsi+8]
0x180026937  test    rax, rax
0x18002693a  jz      short loc_180026942
0x18002693c  mov     rdx, [rdx+30h]
0x180026940  jmp     short loc_18002691A
0x180026942  add     rdx, 18h; pvarSrc
0x180026946  mov     rcx, rdi; pvarDest
0x180026949  call    cs:__imp_PropVariantCopy
0x18002694f  mov     edi, eax
0x180026951  test    eax, eax
0x180026953  jns     short loc_180026980
0x180026955  mov     rcx, [rsp+48h]; this
0x18002695a  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x180026961  mov     r9d, eax; char *
0x180026964  mov     edx, 1D1h; void *
0x180026969  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002696e  test    rbx, rbx
0x180026971  jz      short loc_18002697C
0x180026973  mov     rcx, rbx; lpCriticalSection
0x180026976  call    cs:__imp_LeaveCriticalSection
0x18002697c  mov     eax, edi
0x18002697e  jmp     short loc_180026990
0x180026980  test    rbx, rbx
0x180026983  jz      short loc_18002698E
0x180026985  mov     rcx, rbx; lpCriticalSection
0x180026988  call    cs:__imp_LeaveCriticalSection
0x18002698e  xor     eax, eax
0x180026990  add     rsp, 28h
0x180026994  pop     rdi
0x180026995  pop     rsi
0x180026996  pop     rbp
0x180026997  pop     rbx
0x180026998  retn
```
