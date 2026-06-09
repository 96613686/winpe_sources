# MapsBrokerAsyncOperation::Cancel(bool)

- ea: `0x180007ad0`
- end: `0x180007b90`
- name: `?Cancel@MapsBrokerAsyncOperation@@UEAAJ_N@Z`
- size: `192`
- prototype: `__int64 __fastcall(MapsBrokerAsyncOperation *this, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007948`

## callees

- `0x1800047f0`
- `0x180006214`
- `0x180007ad0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007b39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007b39`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007af7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007b12`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007af7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007b12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007ae5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007ae5`

## string_xrefs

- `0x180007b5b`: `onecoreuap\windows\maps\moshost\client\mapsbrokerasyncoperation.cpp`

## pseudocode

```c
__int64 __fastcall MapsBrokerAsyncOperation::Cancel(MapsBrokerAsyncOperation *this, char a2)
{
  void *v4; // rbp
  DWORD v5; // eax
  unsigned int v6; // r8d
  const char *v7; // r9
  DWORD v8; // ebx
  __int64 v9; // rbx
  int v10; // eax
  unsigned int v11; // ebx
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v4 = (void *)*((_QWORD *)this + 11);
  v5 = WaitForSingleObjectEx(v4, 0, 0);
  v8 = v5;
  if ( v5 != 258 && (v5 || WaitForSingleObjectEx(v4, 0, 0)) )
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB07, v6, v7);
  if ( v8 )
    v9 = *((_QWORD *)this + 7);
  else
    v9 = 0;
  if ( a2 )
    *((_QWORD *)this + 8) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !v9 )
    return 0;
  v10 = (*((__int64 (__fastcall **)(__int64))this + 9))(v9);
  v11 = v10;
  if ( v10 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2A,
    (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\mapsbrokerasyncoperation.cpp",
    (const char *)(unsigned int)v10,
    v13);
  return v11;
}

```

## disassembly

```asm
0x180007ad0  push    rbx
0x180007ad2  push    rbp
0x180007ad3  push    rsi
0x180007ad4  push    rdi
0x180007ad5  push    r14; int
0x180007ad7  sub     rsp, 20h
0x180007adb  mov     rdi, rcx
0x180007ade  mov     r14b, dl
0x180007ae1  add     rcx, 10h; lpCriticalSection
0x180007ae5  call    cs:__imp_EnterCriticalSection
0x180007aeb  mov     rbp, [rdi+58h]
0x180007aef  xor     r8d, r8d; bAlertable
0x180007af2  mov     rcx, rbp; hHandle
0x180007af5  xor     edx, edx; dwMilliseconds
0x180007af7  call    cs:__imp_WaitForSingleObjectEx
0x180007afd  mov     ebx, eax
0x180007aff  cmp     eax, 102h
0x180007b04  jz      short loc_180007B1C
0x180007b06  test    eax, eax
0x180007b08  jnz     short loc_180007B80
0x180007b0a  xor     r8d, r8d; bAlertable
0x180007b0d  xor     edx, edx; dwMilliseconds
0x180007b0f  mov     rcx, rbp; hHandle
0x180007b12  call    cs:__imp_WaitForSingleObjectEx
0x180007b18  test    eax, eax
0x180007b1a  jnz     short loc_180007B80
0x180007b1c  test    ebx, ebx
0x180007b1e  jnz     short loc_180007B24
0x180007b20  xor     ebx, ebx
0x180007b22  jmp     short loc_180007B28
0x180007b24  mov     rbx, [rdi+38h]
0x180007b28  test    r14b, r14b
0x180007b2b  jz      short loc_180007B35
0x180007b2d  mov     qword ptr [rdi+40h], 0
0x180007b35  lea     rcx, [rdi+10h]; lpCriticalSection
0x180007b39  call    cs:__imp_LeaveCriticalSection
0x180007b3f  test    rbx, rbx
0x180007b42  jz      short loc_180007B73
0x180007b44  mov     rax, [rdi+48h]
0x180007b48  mov     rcx, rbx
0x180007b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b50  mov     ebx, eax
0x180007b52  test    eax, eax
0x180007b54  jns     short loc_180007B73
0x180007b56  mov     rcx, [rsp+48h]; this
0x180007b5b  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x180007b62  mov     r9d, eax; char *
0x180007b65  mov     edx, 2Ah ; '*'; void *
0x180007b6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b6f  mov     eax, ebx
0x180007b71  jmp     short loc_180007B75
0x180007b73  xor     eax, eax
0x180007b75  add     rsp, 20h
0x180007b79  pop     r14
0x180007b7b  pop     rdi
0x180007b7c  pop     rsi
0x180007b7d  pop     rbp
0x180007b7e  pop     rbx
0x180007b7f  retn
0x180007b80  mov     rcx, [rsp+48h]; this
0x180007b85  mov     edx, 0B07h; void *
0x180007b8a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
