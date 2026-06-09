# CInkRecoContext::put_RecognitionFlags(InkRecognitionModes)

- ea: `0x1800a85d0`
- end: `0x1800a87b1`
- name: `?put_RecognitionFlags@CInkRecoContext@@UEAAJW4InkRecognitionModes@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(CInkRecoContext *__hidden this, enum InkRecognitionModes)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800365f8`
- `0x180036824`
- `0x180083dc0`
- `0x1800a85d0`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a867d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a867d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a866f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a866f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a869f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a86e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a869f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a86e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8721`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8773`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8721`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8773`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a874f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a874f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInkRecoContext::put_RecognitionFlags(CInkRecoContext *this, unsigned int a2)
{
  __int64 v4; // rdx
  signed int v5; // ebx
  _QWORD *v7; // rsi
  HANDLE EventW; // rax
  signed int LastError; // eax
  _QWORD *v10; // rax
  void *v11; // r14
  __int64 v12; // rbx
  _QWORD *v13; // rax
  void *v14; // rsi
  _BYTE v15[40]; // [rsp+30h] [rbp-28h] BYREF
  DWORD dwindex; // [rsp+68h] [rbp+10h] BYREF

  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v15, (struct _RTL_CRITICAL_SECTION *)((char *)this + 216));
  if ( a2 > 0x7F )
  {
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v15);
    return 2147942487LL;
  }
  v5 = 0;
  if ( *((_QWORD *)this + 33) )
  {
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v15);
    return 2147746359LL;
  }
  try
  {
    if ( *((_QWORD *)this + 12) )
      goto LABEL_8;
    LOBYTE(v4) = 1;
    v5 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 2) + 72LL))((char *)this - 16, v4);
    if ( v5 >= 0 )
    {
      if ( !*((_QWORD *)this + 12) )
      {
LABEL_7:
        v5 = -2147418113;
        goto LABEL_34;
      }
LABEL_8:
      v7 = (_QWORD *)((char *)this + 160);
      if ( !*((_QWORD *)this + 20) )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        *v7 = EventW;
        if ( !EventW )
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
        }
        if ( v5 < 0 )
          goto LABEL_34;
      }
      v10 = CoTaskMemAlloc(8u);
      v11 = v10;
      if ( !v10 )
      {
        v5 = -2147024882;
        goto LABEL_34;
      }
      *v10 = v7;
      v12 = *(_QWORD *)(*((_QWORD *)this + 12) + 16LL);
      if ( v12 )
      {
        if ( *(_QWORD *)(v12 + 16) )
        {
          v13 = CoTaskMemAlloc(0x18u);
          v14 = v13;
          if ( v13 )
          {
            v13[1] = v11;
            *v13 = InkHResultSynchronousCallback;
            *((_DWORD *)v13 + 4) = a2;
            v5 = AddToQueue(v12, 14, v13);
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
        CoTaskMemFree(v11);
        goto LABEL_34;
      }
      dwindex = 0;
      if ( CoWaitForMultipleHandles(0, 0x493E0u, 1u, (LPHANDLE)this + 20, &dwindex) >= 0 )
      {
        v5 = *((_DWORD *)this + 47);
        if ( v5 >= 0 )
          *((_DWORD *)this + 34) = a2;
        goto LABEL_34;
      }
      goto LABEL_7;
    }
  }
  catch ( ... )
  {
    dwindex = ReportWispException();
    v5 = dwindex;
  }
LABEL_34:
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800a85d0  mov     [rsp+arg_0], rbx
0x1800a85d5  mov     [rsp+arg_10], rsi
0x1800a85da  push    rdi
0x1800a85db  push    r14
0x1800a85dd  push    r15
0x1800a85df  sub     rsp, 40h
0x1800a85e3  mov     r15d, edx
0x1800a85e6  mov     rdi, rcx
0x1800a85e9  lea     rdx, [rcx+0D8h]; struct _RTL_CRITICAL_SECTION *
0x1800a85f0  lea     rcx, [rsp+58h+var_28]; this
0x1800a85f5  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800a85fa  nop
0x1800a85fb  cmp     r15d, 7Fh
0x1800a85ff  ja      loc_1800A878E
0x1800a8605  xor     ebx, ebx
0x1800a8607  lea     rcx, [rdi-10h]
0x1800a860b  cmp     [rcx+118h], rbx
0x1800a8612  jz      short loc_1800A8628
0x1800a8614  lea     rcx, [rsp+58h+var_28]; this
0x1800a8619  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a861e  mov     eax, 80040237h
0x1800a8623  jmp     loc_1800A879D
0x1800a8628  cmp     qword ptr [rdi+60h], 0
0x1800a862d  jnz     short loc_1800A8658
0x1800a862f  mov     rax, [rcx]
0x1800a8632  mov     dl, 1
0x1800a8634  mov     rax, [rax+48h]
0x1800a8638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a863d  mov     ebx, eax
0x1800a863f  test    eax, eax
0x1800a8641  js      loc_1800A877A
0x1800a8647  cmp     qword ptr [rdi+60h], 0
0x1800a864c  jnz     short loc_1800A8658
0x1800a864e  mov     ebx, 8000FFFFh
0x1800a8653  jmp     loc_1800A877A
0x1800a8658  lea     rsi, [rdi+0A0h]
0x1800a865f  cmp     qword ptr [rsi], 0
0x1800a8663  jnz     short loc_1800A869A
0x1800a8665  xor     r9d, r9d; lpName
0x1800a8668  xor     r8d, r8d; bInitialState
0x1800a866b  xor     edx, edx; bManualReset
0x1800a866d  xor     ecx, ecx; lpEventAttributes
0x1800a866f  call    cs:__imp_CreateEventW
0x1800a8675  mov     [rsi], rax
0x1800a8678  test    rax, rax
0x1800a867b  jnz     short loc_1800A8692
0x1800a867d  call    cs:__imp_GetLastError
0x1800a8683  mov     ebx, eax
0x1800a8685  test    eax, eax
0x1800a8687  jle     short loc_1800A8692
0x1800a8689  movzx   ebx, ax
0x1800a868c  or      ebx, 80070000h
0x1800a8692  test    ebx, ebx
0x1800a8694  js      loc_1800A877A
0x1800a869a  mov     ecx, 8; cb
0x1800a869f  call    cs:__imp_CoTaskMemAlloc
0x1800a86a5  mov     r14, rax
0x1800a86a8  test    rax, rax
0x1800a86ab  jnz     short loc_1800A86B7
0x1800a86ad  mov     ebx, 8007000Eh
0x1800a86b2  jmp     loc_1800A877A
0x1800a86b7  mov     [rax], rsi
0x1800a86ba  mov     rax, [rdi+60h]
0x1800a86be  mov     rbx, [rax+10h]
0x1800a86c2  test    rbx, rbx
0x1800a86c5  jnz     short loc_1800A86CE
0x1800a86c7  mov     ebx, 80004003h
0x1800a86cc  jmp     short loc_1800A8727
0x1800a86ce  cmp     qword ptr [rbx+10h], 0
0x1800a86d3  jnz     short loc_1800A86DC
0x1800a86d5  mov     ebx, 80040234h
0x1800a86da  jmp     short loc_1800A8727
0x1800a86dc  mov     ecx, 18h; cb
0x1800a86e1  call    cs:__imp_CoTaskMemAlloc
0x1800a86e7  mov     rsi, rax
0x1800a86ea  test    rax, rax
0x1800a86ed  jnz     short loc_1800A86F6
0x1800a86ef  mov     ebx, 8007000Eh
0x1800a86f4  jmp     short loc_1800A8727
0x1800a86f6  mov     [rax+8], r14
0x1800a86fa  lea     rax, ?InkHResultSynchronousCallback@@YAJJPEAE@Z; InkHResultSynchronousCallback(long,uchar *)
0x1800a8701  mov     [rsi], rax
0x1800a8704  mov     [rsi+10h], r15d
0x1800a8708  mov     r8, rsi
0x1800a870b  mov     edx, 0Eh
0x1800a8710  mov     rcx, rbx
0x1800a8713  call    ?AddToQueue@@YAJPEAUtagWispContext@@W4OpType@@PEAX@Z; AddToQueue(tagWispContext *,OpType,void *)
0x1800a8718  mov     ebx, eax
0x1800a871a  test    eax, eax
0x1800a871c  jns     short loc_1800A8727
0x1800a871e  mov     rcx, rsi; pv
0x1800a8721  call    cs:__imp_CoTaskMemFree
0x1800a8727  test    ebx, ebx
0x1800a8729  js      short loc_1800A8770
0x1800a872b  mov     [rsp+58h+dwindex], 0
0x1800a8733  lea     r9, [rdi+0A0h]; pHandles
0x1800a873a  lea     rax, [rsp+58h+dwindex]
0x1800a873f  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x1800a8744  mov     edx, 493E0h; dwTimeout
0x1800a8749  xor     ecx, ecx; dwFlags
0x1800a874b  lea     r8d, [rcx+1]; cHandles
0x1800a874f  call    cs:__imp_CoWaitForMultipleHandles
0x1800a8755  test    eax, eax
0x1800a8757  js      loc_1800A864E
0x1800a875d  mov     ebx, [rdi+0BCh]
0x1800a8763  test    ebx, ebx
0x1800a8765  js      short loc_1800A877A
0x1800a8767  mov     [rdi+88h], r15d
0x1800a876e  jmp     short loc_1800A877A
0x1800a8770  mov     rcx, r14; pv
0x1800a8773  call    cs:__imp_CoTaskMemFree
0x1800a8779  nop
0x1800a877a  jmp     short loc_1800A8780
0x1800a877c  mov     ebx, [rsp+58h+dwindex]
0x1800a8780  lea     rcx, [rsp+58h+var_28]; this
0x1800a8785  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a878a  mov     eax, ebx
0x1800a878c  jmp     short loc_1800A879D
0x1800a878e  lea     rcx, [rsp+58h+var_28]; this
0x1800a8793  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a8798  mov     eax, 80070057h
0x1800a879d  mov     rbx, [rsp+58h+arg_0]
0x1800a87a2  mov     rsi, [rsp+58h+arg_10]
0x1800a87a7  add     rsp, 40h
0x1800a87ab  pop     r15
0x1800a87ad  pop     r14
0x1800a87af  pop     rdi
0x1800a87b0  retn
```
