# CInkRecoContext::put_CharacterAutoCompletionMode(InkRecognizerCharacterAutoCompletionMode)

- ea: `0x1800a7ab0`
- end: `0x1800a7c76`
- name: `?put_CharacterAutoCompletionMode@CInkRecoContext@@UEAAJW4InkRecognizerCharacterAutoCompletionMode@@@Z`
- size: `454`
- prototype: `__int64 __fastcall(CInkRecoContext *__hidden this, enum InkRecognizerCharacterAutoCompletionMode)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800365f8`
- `0x180036824`
- `0x180083dc0`
- `0x1800a7ab0`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7b3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7b3a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a7b2c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a7b2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a7b5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a7ba2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a7b5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a7ba2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a7be2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a7c3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a7be2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a7c3b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a7c16`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a7c16`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CInkRecoContext::put_CharacterAutoCompletionMode(CInkRecoContext *this, unsigned int a2)
{
  __int64 v4; // rdx
  signed int v5; // ebx
  _QWORD *v6; // rsi
  HANDLE EventW; // rax
  signed int LastError; // eax
  _QWORD *v9; // rax
  void *v10; // r14
  __int64 v11; // rbx
  int v12; // r15d
  _QWORD *v13; // rax
  void *v14; // rsi
  _BYTE v16[72]; // [rsp+30h] [rbp-48h] BYREF
  DWORD dwindex; // [rsp+88h] [rbp+10h] BYREF

  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v16, (struct _RTL_CRITICAL_SECTION *)((char *)this + 216));
  if ( a2 <= 2 )
  {
    v5 = 0;
    if ( *((_QWORD *)this + 12) )
      goto LABEL_6;
    LOBYTE(v4) = 1;
    v5 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 2) + 72LL))((char *)this - 16, v4);
    if ( v5 < 0 )
    {
LABEL_26:
      CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v16);
      return (unsigned int)v5;
    }
    if ( *((_QWORD *)this + 12) )
    {
LABEL_6:
      v6 = (_QWORD *)((char *)this + 160);
      if ( !*((_QWORD *)this + 20) )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        *v6 = EventW;
        if ( !EventW )
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
        }
        if ( v5 < 0 )
          goto LABEL_26;
      }
      v9 = CoTaskMemAlloc(8u);
      v10 = v9;
      if ( !v9 )
      {
        v5 = -2147024882;
        goto LABEL_26;
      }
      *v9 = v6;
      v11 = *(_QWORD *)(*((_QWORD *)this + 12) + 16LL);
      if ( v11 )
      {
        if ( *(_QWORD *)(v11 + 16) )
        {
          v12 = *((_DWORD *)this + 29);
          v13 = CoTaskMemAlloc(0x18u);
          v14 = v13;
          if ( v13 )
          {
            v13[1] = v10;
            *v13 = InkHResultSynchronousCallback;
            *((_DWORD *)v13 + 4) = v12;
            v5 = AddToQueue(v11, 20, v13);
            if ( v5 < 0 )
              CoTaskMemFree(v14);
          }
          else
          {
            v5 = -2147024882;
          }
        }
        else
        {
          v5 = -2147220940;
        }
      }
      else
      {
        v5 = -2147467261;
      }
      if ( v5 < 0 )
      {
        CoTaskMemFree(v10);
        goto LABEL_26;
      }
      dwindex = 0;
      if ( CoWaitForMultipleHandles(0, 0x493E0u, 1u, (LPHANDLE)this + 20, &dwindex) >= 0 )
      {
        v5 = *((_DWORD *)this + 47);
        if ( v5 >= 0 )
        {
          *((_BYTE *)this + 112) = 1;
          *((_DWORD *)this + 29) = a2;
        }
        goto LABEL_26;
      }
    }
    v5 = -2147418113;
    goto LABEL_26;
  }
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v16);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800a7ab0  push    rbx
0x1800a7ab2  push    rsi
0x1800a7ab3  push    rdi
0x1800a7ab4  push    r12
0x1800a7ab6  push    r14
0x1800a7ab8  push    r15
0x1800a7aba  sub     rsp, 48h
0x1800a7abe  mov     r12d, edx
0x1800a7ac1  mov     rdi, rcx
0x1800a7ac4  lea     rdx, [rcx+0D8h]; struct _RTL_CRITICAL_SECTION *
0x1800a7acb  lea     rcx, [rsp+78h+var_48]; this
0x1800a7ad0  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800a7ad5  nop
0x1800a7ad6  cmp     r12d, 2
0x1800a7ada  ja      loc_1800A7C59
0x1800a7ae0  xor     ebx, ebx
0x1800a7ae2  lea     rcx, [rdi-10h]
0x1800a7ae6  cmp     [rcx+70h], rbx
0x1800a7aea  jnz     short loc_1800A7B15
0x1800a7aec  mov     rax, [rcx]
0x1800a7aef  mov     dl, 1
0x1800a7af1  mov     rax, [rax+48h]
0x1800a7af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7afa  mov     ebx, eax
0x1800a7afc  test    eax, eax
0x1800a7afe  js      loc_1800A7C42
0x1800a7b04  cmp     qword ptr [rdi+60h], 0
0x1800a7b09  jnz     short loc_1800A7B15
0x1800a7b0b  mov     ebx, 8000FFFFh
0x1800a7b10  jmp     loc_1800A7C42
0x1800a7b15  lea     rsi, [rdi+0A0h]
0x1800a7b1c  cmp     qword ptr [rsi], 0
0x1800a7b20  jnz     short loc_1800A7B57
0x1800a7b22  xor     r9d, r9d; lpName
0x1800a7b25  xor     r8d, r8d; bInitialState
0x1800a7b28  xor     edx, edx; bManualReset
0x1800a7b2a  xor     ecx, ecx; lpEventAttributes
0x1800a7b2c  call    cs:__imp_CreateEventW
0x1800a7b32  mov     [rsi], rax
0x1800a7b35  test    rax, rax
0x1800a7b38  jnz     short loc_1800A7B4F
0x1800a7b3a  call    cs:__imp_GetLastError
0x1800a7b40  mov     ebx, eax
0x1800a7b42  test    eax, eax
0x1800a7b44  jle     short loc_1800A7B4F
0x1800a7b46  movzx   ebx, ax
0x1800a7b49  or      ebx, 80070000h
0x1800a7b4f  test    ebx, ebx
0x1800a7b51  js      loc_1800A7C42
0x1800a7b57  mov     ecx, 8; cb
0x1800a7b5c  call    cs:__imp_CoTaskMemAlloc
0x1800a7b62  mov     r14, rax
0x1800a7b65  test    rax, rax
0x1800a7b68  jnz     short loc_1800A7B74
0x1800a7b6a  mov     ebx, 8007000Eh
0x1800a7b6f  jmp     loc_1800A7C42
0x1800a7b74  mov     [rax], rsi
0x1800a7b77  mov     rax, [rdi+60h]
0x1800a7b7b  mov     rbx, [rax+10h]
0x1800a7b7f  test    rbx, rbx
0x1800a7b82  jnz     short loc_1800A7B8B
0x1800a7b84  mov     ebx, 80004003h
0x1800a7b89  jmp     short loc_1800A7BE8
0x1800a7b8b  cmp     qword ptr [rbx+10h], 0
0x1800a7b90  jnz     short loc_1800A7B99
0x1800a7b92  mov     ebx, 80040234h
0x1800a7b97  jmp     short loc_1800A7BE8
0x1800a7b99  mov     r15d, [rdi+74h]
0x1800a7b9d  mov     ecx, 18h; cb
0x1800a7ba2  call    cs:__imp_CoTaskMemAlloc
0x1800a7ba8  mov     rsi, rax
0x1800a7bab  test    rax, rax
0x1800a7bae  jnz     short loc_1800A7BB7
0x1800a7bb0  mov     ebx, 8007000Eh
0x1800a7bb5  jmp     short loc_1800A7BE8
0x1800a7bb7  mov     [rax+8], r14
0x1800a7bbb  lea     rax, ?InkHResultSynchronousCallback@@YAJJPEAE@Z; InkHResultSynchronousCallback(long,uchar *)
0x1800a7bc2  mov     [rsi], rax
0x1800a7bc5  mov     [rsi+10h], r15d
0x1800a7bc9  mov     r8, rsi
0x1800a7bcc  mov     edx, 14h
0x1800a7bd1  mov     rcx, rbx
0x1800a7bd4  call    ?AddToQueue@@YAJPEAUtagWispContext@@W4OpType@@PEAX@Z; AddToQueue(tagWispContext *,OpType,void *)
0x1800a7bd9  mov     ebx, eax
0x1800a7bdb  test    eax, eax
0x1800a7bdd  jns     short loc_1800A7BE8
0x1800a7bdf  mov     rcx, rsi; pv
0x1800a7be2  call    cs:__imp_CoTaskMemFree
0x1800a7be8  test    ebx, ebx
0x1800a7bea  js      short loc_1800A7C38
0x1800a7bec  mov     [rsp+78h+dwindex], 0
0x1800a7bf7  lea     r9, [rdi+0A0h]; pHandles
0x1800a7bfe  lea     rax, [rsp+78h+dwindex]
0x1800a7c06  mov     [rsp+78h+lpdwindex], rax; lpdwindex
0x1800a7c0b  mov     edx, 493E0h; dwTimeout
0x1800a7c10  xor     ecx, ecx; dwFlags
0x1800a7c12  lea     r8d, [rcx+1]; cHandles
0x1800a7c16  call    cs:__imp_CoWaitForMultipleHandles
0x1800a7c1c  test    eax, eax
0x1800a7c1e  js      loc_1800A7B0B
0x1800a7c24  mov     ebx, [rdi+0BCh]
0x1800a7c2a  test    ebx, ebx
0x1800a7c2c  js      short loc_1800A7C42
0x1800a7c2e  mov     byte ptr [rdi+70h], 1
0x1800a7c32  mov     [rdi+74h], r12d
0x1800a7c36  jmp     short loc_1800A7C42
0x1800a7c38  mov     rcx, r14; pv
0x1800a7c3b  call    cs:__imp_CoTaskMemFree
0x1800a7c41  nop
0x1800a7c42  jmp     short loc_1800A7C4B
0x1800a7c44  mov     ebx, [rsp+78h+dwindex]
0x1800a7c4b  lea     rcx, [rsp+78h+var_48]; this
0x1800a7c50  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a7c55  mov     eax, ebx
0x1800a7c57  jmp     short loc_1800A7C68
0x1800a7c59  lea     rcx, [rsp+78h+var_48]; this
0x1800a7c5e  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a7c63  mov     eax, 80070057h
0x1800a7c68  add     rsp, 48h
0x1800a7c6c  pop     r15
0x1800a7c6e  pop     r14
0x1800a7c70  pop     r12
0x1800a7c72  pop     rdi
0x1800a7c73  pop     rsi
0x1800a7c74  pop     rbx
0x1800a7c75  retn
```
