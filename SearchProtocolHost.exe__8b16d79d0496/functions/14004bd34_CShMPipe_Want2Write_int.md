# CShMPipe::Want2Write(int)

- ea: `0x14004bd34`
- end: `0x14004bf46`
- name: `?Want2Write@CShMPipe@@QEAAJH@Z`
- size: `530`
- prototype: `__int64 __fastcall(CShMPipe *__hidden this, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14003cb14`
- `0x14003cd00`

## callees

- `0x140015958`
- `0x14004aae0`
- `0x14004ab24`
- `0x14004abac`
- `0x14004b640`
- `0x14004b954`
- `0x14004bd34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14004be3c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14004be3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004be00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004bee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004be00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004bee3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004bf0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004bf0e`

## string_xrefs

- `0x14004bef8`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\shmpipe.cxx"`
- `0x14004bee9`: `[UtilCommon] Failed to release Receive semaphore! 0x%08x`

## pseudocode

```c
signed int __fastcall CShMPipe::Want2Write(CShMPipe *this)
{
  DWORD v1; // r15d
  int v3; // esi
  int v4; // r12d
  signed int result; // eax
  DWORD WaitHandles; // ebp
  unsigned int v7; // r8d
  unsigned int v8; // edi
  __int64 v9; // rcx
  int v10; // edx
  int v11; // eax
  unsigned int v12; // eax
  DWORD v13; // edi
  DWORD v14; // ebp
  unsigned int v15; // r8d
  unsigned int v16; // r10d
  DWORD v17; // ecx
  DWORD v18; // eax
  DWORD LastError; // eax

  v1 = 10000;
  if ( *((_DWORD *)this + 36) <= 0x270Fu )
    v1 = *((_DWORD *)this + 36);
  v3 = *(_DWORD *)(*((_QWORD *)this + 10) + 136LL);
  v4 = *(_DWORD *)(*((_QWORD *)this + 10) + 144LL);
  if ( *((_WORD *)this + 4) )
    return 0;
  if ( *((_WORD *)this + 5) )
  {
    WaitHandles = CShMPipe::GetWaitHandles(this, *((void **)this + 11));
    v8 = 0;
    while ( 1 )
    {
      v9 = *((_QWORD *)this + 10);
      v10 = *(_DWORD *)(v9 + 128);
      if ( (v10 & 0x40000000) != 0 )
        break;
      if ( v10 >= 0 )
        return -2147217996;
      v11 = WaitForMultipleObjectsLP(WaitHandles, (HANDLE *)this + 5, 0x32u, *((_BYTE *)this + 376));
      if ( v11 != 258 )
      {
        if ( v11 == -1 )
          goto LABEL_15;
        if ( v11 )
          return -2147217996;
      }
      v12 = *((_DWORD *)this + 36);
      if ( v12 != -1 )
      {
        v8 += 50;
        if ( v8 >= v12 )
          return -2147023436;
      }
    }
    if ( v3 != v4 )
      *(_DWORD *)(v9 + 144) = v3;
    BitOp::InterlockedClearFlag((BitOp *)(*((_QWORD *)this + 10) + 128LL), (unsigned int *)0x40000000, v7);
    SetEvent(*((HANDLE *)this + 13));
    if ( CShMPipe::ReleaseOperationMutex(this, *((void *const *)this + 15)) >= 0 )
    {
      *((_WORD *)this + 5) = 0;
      goto LABEL_21;
    }
    if ( *(int *)(*((_QWORD *)this + 10) + 128LL) >= 0 )
    {
      SetLastError(0xE9u);
    }
    else
    {
      LastError = GetLastError();
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutild\\\\shmpipe.cxx\"",
        (const wchar_t *)0x70D,
        (unsigned int)L"[UtilCommon] Failed to release Receive semaphore! 0x%08x",
        (const wchar_t *)LastError);
    }
LABEL_15:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
LABEL_21:
    v13 = 0;
    v14 = CShMPipe::GetWaitHandles(this, *((void **)this + 14));
    while ( 1 )
    {
      WaitForMultipleObjectsLP(v14, (HANDLE *)this + 5, v1, *((_BYTE *)this + 376));
      if ( v3 != v4 )
        *(_DWORD *)(*((_QWORD *)this + 10) + 144LL) = v3;
      BitOp::InterlockedClearFlag((BitOp *)(*((_QWORD *)this + 10) + 128LL), (unsigned int *)0x40000000, v15);
      if ( *(int *)(*((_QWORD *)this + 10) + 128LL) >= 0 )
        break;
      if ( v16 != 258 )
      {
        result = GetHRFromDW(v16);
        if ( result < 0 )
          return result;
        *((_WORD *)this + 4) = 1;
        return 0;
      }
      v17 = *((_DWORD *)this + 36);
      v18 = v1 + v13;
      if ( v17 == -1 )
        v18 = v13;
      v13 = v18;
      if ( v18 >= v17 )
        return -2147023436;
    }
    return -2147217996;
  }
  return result;
}

```

## disassembly

```asm
0x14004bd34  push    rbx
0x14004bd36  push    rbp
0x14004bd37  push    rsi
0x14004bd38  push    rdi
0x14004bd39  push    r12
0x14004bd3b  push    r13
0x14004bd3d  push    r14
0x14004bd3f  push    r15
0x14004bd41  sub     rsp, 28h
0x14004bd45  mov     eax, [rcx+90h]
0x14004bd4b  mov     r15d, 2710h
0x14004bd51  cmp     eax, 270Fh
0x14004bd56  mov     rbx, rcx
0x14004bd59  cmovbe  r15d, eax
0x14004bd5d  mov     rax, [rcx+50h]
0x14004bd61  xor     r13d, r13d
0x14004bd64  mov     esi, [rax+88h]
0x14004bd6a  mov     rax, [rcx+50h]
0x14004bd6e  mov     r12d, [rax+90h]
0x14004bd75  cmp     [rcx+8], r13w
0x14004bd7a  jz      short loc_14004BD83
0x14004bd7c  xor     eax, eax
0x14004bd7e  jmp     loc_14004BF35
0x14004bd83  or      r14d, 0FFFFFFFFh
0x14004bd87  cmp     [rcx+0Ah], r13w
0x14004bd8c  jz      loc_14004BE5B
0x14004bd92  mov     rdx, [rcx+58h]; void *
0x14004bd96  call    ?GetWaitHandles@CShMPipe@@IEAAKPEAX@Z; CShMPipe::GetWaitHandles(void *)
0x14004bd9b  mov     ebp, eax
0x14004bd9d  mov     edi, r13d
0x14004bda0  mov     rcx, [rbx+50h]
0x14004bda4  mov     edx, [rcx+80h]
0x14004bdaa  bt      edx, 1Eh
0x14004bdae  jb      short loc_14004BE1B
0x14004bdb0  test    edx, edx
0x14004bdb2  jns     loc_14004BF30
0x14004bdb8  mov     r9b, [rbx+178h]
0x14004bdbf  lea     rdx, [rbx+28h]; pHandles
0x14004bdc3  mov     r8d, 32h ; '2'; dwMilliseconds
0x14004bdc9  mov     ecx, ebp; nCount
0x14004bdcb  call    WaitForMultipleObjectsLP
0x14004bdd0  cmp     eax, 102h
0x14004bdd5  jz      short loc_14004BDE4
0x14004bdd7  cmp     eax, r14d
0x14004bdda  jz      short loc_14004BE00
0x14004bddc  test    eax, eax
0x14004bdde  jnz     loc_14004BF30
0x14004bde4  mov     eax, [rbx+90h]
0x14004bdea  cmp     eax, r14d
0x14004bded  jz      short loc_14004BDA0
0x14004bdef  add     edi, 32h ; '2'
0x14004bdf2  cmp     edi, eax
0x14004bdf4  jb      short loc_14004BDA0
0x14004bdf6  mov     eax, 800705B4h
0x14004bdfb  jmp     loc_14004BF35
0x14004be00  call    cs:__imp_GetLastError
0x14004be06  test    eax, eax
0x14004be08  jle     loc_14004BF35
0x14004be0e  movzx   eax, ax
0x14004be11  or      eax, 80070000h
0x14004be16  jmp     loc_14004BF35
0x14004be1b  cmp     esi, r12d
0x14004be1e  jz      short loc_14004BE26
0x14004be20  mov     [rcx+90h], esi
0x14004be26  mov     rcx, [rbx+50h]
0x14004be2a  mov     edx, 40000000h; unsigned int *
0x14004be2f  sub     rcx, 0FFFFFFFFFFFFFF80h; this
0x14004be33  call    ?InterlockedClearFlag@BitOp@@YAXAEAKK@Z; BitOp::InterlockedClearFlag(ulong &,ulong)
0x14004be38  mov     rcx, [rbx+68h]; hEvent
0x14004be3c  call    cs:__imp_SetEvent
0x14004be42  mov     rdx, [rbx+78h]; void *
0x14004be46  mov     rcx, rbx; this
0x14004be49  call    ?ReleaseOperationMutex@CShMPipe@@IEAAJQEAX@Z; CShMPipe::ReleaseOperationMutex(void * const)
0x14004be4e  test    eax, eax
0x14004be50  js      loc_14004BED6
0x14004be56  mov     [rbx+0Ah], r13w
0x14004be5b  mov     rdx, [rbx+70h]; void *
0x14004be5f  mov     rcx, rbx; this
0x14004be62  mov     edi, r13d
0x14004be65  call    ?GetWaitHandles@CShMPipe@@IEAAKPEAX@Z; CShMPipe::GetWaitHandles(void *)
0x14004be6a  mov     ebp, eax
0x14004be6c  mov     r9b, [rbx+178h]
0x14004be73  lea     rdx, [rbx+28h]; pHandles
0x14004be77  mov     r8d, r15d; dwMilliseconds
0x14004be7a  mov     ecx, ebp; nCount
0x14004be7c  call    WaitForMultipleObjectsLP
0x14004be81  mov     r10d, eax
0x14004be84  cmp     esi, r12d
0x14004be87  jz      short loc_14004BE93
0x14004be89  mov     rcx, [rbx+50h]
0x14004be8d  mov     [rcx+90h], esi
0x14004be93  mov     rcx, [rbx+50h]
0x14004be97  mov     edx, 40000000h; unsigned int *
0x14004be9c  sub     rcx, 0FFFFFFFFFFFFFF80h; this
0x14004bea0  call    ?InterlockedClearFlag@BitOp@@YAXAEAKK@Z; BitOp::InterlockedClearFlag(ulong &,ulong)
0x14004bea5  mov     rcx, [rbx+50h]
0x14004bea9  cmp     [rcx+80h], r13d
0x14004beb0  jge     short loc_14004BF30
0x14004beb2  cmp     r10d, 102h
0x14004beb9  jnz     short loc_14004BF19
0x14004bebb  mov     ecx, [rbx+90h]
0x14004bec1  lea     eax, [r15+rdi]
0x14004bec5  cmp     ecx, 0FFFFFFFFh
0x14004bec8  cmovz   eax, edi
0x14004becb  mov     edi, eax
0x14004becd  cmp     eax, ecx
0x14004becf  jb      short loc_14004BE6C
0x14004bed1  jmp     loc_14004BDF6
0x14004bed6  mov     rax, [rbx+50h]
0x14004beda  cmp     [rax+80h], r13d
0x14004bee1  jge     short loc_14004BF09
0x14004bee3  call    cs:__imp_GetLastError
0x14004bee9  lea     r8, aUtilcommonFail_0; "[UtilCommon] Failed to release Receive "...
0x14004bef0  mov     edx, 70Dh; wchar_t *
0x14004bef5  mov     r9d, eax; wchar_t *
0x14004bef8  lea     rcx, aOnecoreuapBase_6; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x14004beff  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x14004bf04  jmp     loc_14004BE00
0x14004bf09  mov     ecx, 0E9h; dwErrCode
0x14004bf0e  call    cs:__imp_SetLastError
0x14004bf14  jmp     loc_14004BE00
0x14004bf19  mov     ecx, r10d
0x14004bf1c  call    GetHRFromDW
0x14004bf21  test    eax, eax
0x14004bf23  js      short loc_14004BF35
0x14004bf25  mov     word ptr [rbx+8], 1
0x14004bf2b  jmp     loc_14004BD7C
0x14004bf30  mov     eax, 80040DB4h
0x14004bf35  add     rsp, 28h
0x14004bf39  pop     r15
0x14004bf3b  pop     r14
0x14004bf3d  pop     r13
0x14004bf3f  pop     r12
0x14004bf41  pop     rdi
0x14004bf42  pop     rsi
0x14004bf43  pop     rbp
0x14004bf44  pop     rbx
0x14004bf45  retn
```
