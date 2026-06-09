# CInkRecoContext::put_EnabledUnicodeRanges(tagVARIANT)

- ea: `0x1800a7ed0`
- end: `0x1800a815e`
- name: `?put_EnabledUnicodeRanges@CInkRecoContext@@UEAAJUtagVARIANT@@@Z`
- size: `654`
- prototype: `int(CInkRecoContext *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002740`
- `0x18000a730`
- `0x180010350`
- `0x1800365f8`
- `0x180036824`
- `0x180039098`
- `0x180084d2c`
- `0x1800a7ed0`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7f5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7f5d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a7f4e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a7f4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a80b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a80b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8120`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8120`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a8109`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a8109`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInkRecoContext::put_EnabledUnicodeRanges(CInkRecoContext *this, struct tagVARIANT *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  _QWORD *v6; // r12
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v9; // eax
  int v10; // r14d
  DWORD v11; // r15d
  struct tagCHARACTER_RANGE *v12; // rdi
  DWORD v13; // ecx
  unsigned __int8 *v14; // rdx
  int v15; // eax
  int v16; // r10d
  int v17; // r8d
  _QWORD *v18; // rax
  int (*v19)(int, unsigned __int8 *); // r9
  void *v20; // r14
  _BYTE v22[72]; // [rsp+30h] [rbp-48h] BYREF
  DWORD dwindex; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v24; // [rsp+88h] [rbp+10h] BYREF
  unsigned __int8 *v25; // [rsp+90h] [rbp+18h] BYREF

  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v22, (struct _RTL_CRITICAL_SECTION *)((char *)this + 152));
  if ( (((a2->vt & 0xBFFF) - 8195) & 0xFFEF) != 0 )
  {
    v5 = -2147024809;
    goto LABEL_44;
  }
  v5 = 0;
  if ( *((_QWORD *)this + 25) )
  {
    v5 = -2147220937;
    goto LABEL_44;
  }
  try
  {
    v6 = (_QWORD *)((char *)this + 96);
    if ( !*((_QWORD *)this + 12) )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      *v6 = EventW;
      if ( !EventW )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( v5 < 0 )
          goto LABEL_44;
      }
    }
    if ( *((_QWORD *)this + 4)
      || (LOBYTE(v4) = 1,
          v5 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 10) + 72LL))((char *)this - 80, v4),
          v5 < 0) )
    {
      if ( v5 < 0 )
        goto LABEL_44;
    }
    else if ( !*((_QWORD *)this + 4) )
    {
      v5 = -2147418113;
      goto LABEL_44;
    }
    dwindex = 0;
    v25 = 0;
    v9 = AccessVariantData(a2, &v25, &dwindex, &v24, 0, 0);
    v5 = v9;
    if ( v9 >= 0 )
    {
      v10 = v9;
      if ( (dwindex & 7) != 0 )
        v10 = -2147024809;
      v11 = dwindex >> 3;
      v12 = (struct tagCHARACTER_RANGE *)WinMalloc(saturated_mul(dwindex >> 3, 4u));
      if ( v12 )
      {
        v13 = 0;
        if ( v11 )
        {
          v14 = v25;
          do
          {
            if ( v10 < 0 )
              break;
            v15 = 2 * v13;
            v16 = *(unsigned __int16 *)&v14[8 * v13];
            if ( *(_DWORD *)&v14[8 * v13] == v16
              && (v17 = *(unsigned __int16 *)&v14[4 * v15 + 4], *(_DWORD *)&v14[4 * v15 + 4] == v17) )
            {
              v12[v13].wcLow = v16;
              v12[v13].cChars = v17;
            }
            else
            {
              v10 = -2147024809;
            }
            ++v13;
          }
          while ( v13 < v11 );
          v5 = -2147024882;
          goto LABEL_31;
        }
        v5 = -2147024882;
      }
      else
      {
        v5 = -2147024882;
        v10 = -2147024882;
      }
      v14 = v25;
LABEL_31:
      UnaccessVariantData(a2, v14);
      if ( v10 < 0 )
      {
        v5 = v10;
      }
      else
      {
        v18 = CoTaskMemAlloc(8u);
        v20 = v18;
        if ( v18 )
        {
          *v18 = v6;
          v5 = BackgroundSetEnabledUnicodeRanges(*(_QWORD **)(*((_QWORD *)this + 4) + 16LL), v11, v12, v19, v18);
          if ( v5 < 0 )
          {
            CoTaskMemFree(v20);
          }
          else
          {
            dwindex = 0;
            v5 = -2147418113;
            if ( CoWaitForMultipleHandles(0, 0x493E0u, 1u, (LPHANDLE)this + 12, &dwindex) >= 0 )
              v5 = *((_DWORD *)this + 31);
          }
        }
      }
      if ( v12 )
        WinFree(v12);
    }
  }
  catch ( ... )
  {
    dwindex = ReportWispException();
    v5 = dwindex;
  }
LABEL_44:
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v22);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800a7ed0  push    rbx
0x1800a7ed2  push    rsi
0x1800a7ed3  push    rdi
0x1800a7ed4  push    r12
0x1800a7ed6  push    r13
0x1800a7ed8  push    r14
0x1800a7eda  push    r15
0x1800a7edc  sub     rsp, 40h
0x1800a7ee0  mov     r13, rdx
0x1800a7ee3  mov     rsi, rcx
0x1800a7ee6  lea     rdx, [rcx+98h]; struct _RTL_CRITICAL_SECTION *
0x1800a7eed  lea     rcx, [rsp+78h+var_48]; this
0x1800a7ef2  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800a7ef7  nop
0x1800a7ef8  movzx   eax, word ptr [r13+0]
0x1800a7efd  mov     ecx, 0BFFFh
0x1800a7f02  and     ax, cx
0x1800a7f05  mov     ecx, 2003h
0x1800a7f0a  sub     ax, cx
0x1800a7f0d  mov     ecx, 0FFEFh
0x1800a7f12  test    cx, ax
0x1800a7f15  jz      short loc_1800A7F21
0x1800a7f17  mov     ebx, 80070057h
0x1800a7f1c  jmp     loc_1800A8142
0x1800a7f21  xor     r14d, r14d
0x1800a7f24  mov     ebx, r14d
0x1800a7f27  cmp     [rsi+0C8h], r14
0x1800a7f2e  jz      short loc_1800A7F3A
0x1800a7f30  mov     ebx, 80040237h
0x1800a7f35  jmp     loc_1800A8142
0x1800a7f3a  lea     r12, [rsi+60h]
0x1800a7f3e  cmp     [r12], r14
0x1800a7f42  jnz     short loc_1800A7F7A
0x1800a7f44  xor     r9d, r9d; lpName
0x1800a7f47  xor     r8d, r8d; bInitialState
0x1800a7f4a  xor     edx, edx; bManualReset
0x1800a7f4c  xor     ecx, ecx; lpEventAttributes
0x1800a7f4e  call    cs:__imp_CreateEventW
0x1800a7f54  mov     [r12], rax
0x1800a7f58  test    rax, rax
0x1800a7f5b  jnz     short loc_1800A7F7A
0x1800a7f5d  call    cs:__imp_GetLastError
0x1800a7f63  mov     ebx, eax
0x1800a7f65  test    eax, eax
0x1800a7f67  jle     short loc_1800A7F72
0x1800a7f69  movzx   ebx, ax
0x1800a7f6c  or      ebx, 80070000h
0x1800a7f72  test    ebx, ebx
0x1800a7f74  js      loc_1800A8139
0x1800a7f7a  cmp     [rsi+20h], r14
0x1800a7f7e  jnz     short loc_1800A7FA9
0x1800a7f80  mov     rax, [rsi-50h]
0x1800a7f84  mov     dl, 1
0x1800a7f86  lea     rcx, [rsi-50h]
0x1800a7f8a  mov     rax, [rax+48h]
0x1800a7f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7f93  mov     ebx, eax
0x1800a7f95  test    eax, eax
0x1800a7f97  js      short loc_1800A7FA9
0x1800a7f99  cmp     [rsi+20h], r14
0x1800a7f9d  jnz     short loc_1800A7FB1
0x1800a7f9f  mov     ebx, 8000FFFFh
0x1800a7fa4  jmp     loc_1800A8139
0x1800a7fa9  test    ebx, ebx
0x1800a7fab  js      loc_1800A8139
0x1800a7fb1  mov     [rsp+78h+dwindex], r14d
0x1800a7fb9  mov     [rsp+78h+arg_10], r14
0x1800a7fc1  mov     [rsp+78h+var_50], r14; unsigned __int16 *
0x1800a7fc6  mov     [rsp+78h+lpdwindex], r14; bool *
0x1800a7fcb  lea     r9, [rsp+78h+arg_8]; unsigned int *
0x1800a7fd3  lea     r8, [rsp+78h+dwindex]; unsigned int *
0x1800a7fdb  lea     rdx, [rsp+78h+arg_10]; unsigned __int8 **
0x1800a7fe3  mov     rcx, r13; struct tagVARIANT *
0x1800a7fe6  call    ?AccessVariantData@@YAJPEBUtagVARIANT@@PEAPEAEPEAK2PEA_NPEAG@Z; AccessVariantData(tagVARIANT const *,uchar * *,ulong *,ulong *,bool *,ushort *)
0x1800a7feb  mov     ebx, eax
0x1800a7fed  test    eax, eax
0x1800a7fef  js      loc_1800A8139
0x1800a7ff5  mov     r15d, [rsp+78h+dwindex]
0x1800a7ffd  test    r15b, 7
0x1800a8001  mov     r14d, eax
0x1800a8004  mov     ebx, 80070057h
0x1800a8009  cmovnz  r14d, ebx
0x1800a800d  shr     r15d, 3
0x1800a8011  mov     ecx, r15d
0x1800a8014  mov     eax, 4
0x1800a8019  mul     rcx
0x1800a801c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a8023  cmovb   rax, rcx
0x1800a8027  mov     rcx, rax; unsigned __int64
0x1800a802a  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800a802f  mov     rdi, rax
0x1800a8032  test    rax, rax
0x1800a8035  jnz     short loc_1800A8041
0x1800a8037  mov     ebx, 8007000Eh
0x1800a803c  mov     r14d, ebx
0x1800a803f  jmp     short loc_1800A8099
0x1800a8041  xor     ecx, ecx
0x1800a8043  test    r15d, r15d
0x1800a8046  jz      short loc_1800A8094
0x1800a8048  mov     rdx, [rsp+78h+arg_10]
0x1800a8050  test    r14d, r14d
0x1800a8053  js      short loc_1800A808D
0x1800a8055  lea     eax, [rcx+rcx]
0x1800a8058  movsxd  r9, eax
0x1800a805b  movzx   r10d, word ptr [rdx+r9*4]
0x1800a8060  cmp     [rdx+r9*4], r10d
0x1800a8064  jnz     short loc_1800A8083
0x1800a8066  movzx   r8d, word ptr [rdx+r9*4+4]
0x1800a806c  cmp     [rdx+r9*4+4], r8d
0x1800a8071  jnz     short loc_1800A8083
0x1800a8073  movsxd  rax, ecx
0x1800a8076  mov     [rdi+rax*4], r10w
0x1800a807b  mov     [rdi+rax*4+2], r8w
0x1800a8081  jmp     short loc_1800A8086
0x1800a8083  mov     r14d, ebx
0x1800a8086  inc     ecx
0x1800a8088  cmp     ecx, r15d
0x1800a808b  jb      short loc_1800A8050
0x1800a808d  mov     ebx, 8007000Eh
0x1800a8092  jmp     short loc_1800A80A1
0x1800a8094  mov     ebx, 8007000Eh
0x1800a8099  mov     rdx, [rsp+78h+arg_10]; unsigned __int8 *
0x1800a80a1  mov     rcx, r13; struct tagVARIANT *
0x1800a80a4  call    ?UnaccessVariantData@@YAXPEBUtagVARIANT@@PEAE@Z; UnaccessVariantData(tagVARIANT const *,uchar *)
0x1800a80a9  test    r14d, r14d
0x1800a80ac  js      short loc_1800A8128
0x1800a80ae  mov     ecx, 8; cb
0x1800a80b3  call    cs:__imp_CoTaskMemAlloc
0x1800a80b9  mov     r14, rax
0x1800a80bc  test    rax, rax
0x1800a80bf  jz      short loc_1800A812B
0x1800a80c1  mov     [rax], r12
0x1800a80c4  mov     rcx, [rsi+20h]
0x1800a80c8  mov     [rsp+78h+lpdwindex], rax; void *
0x1800a80cd  mov     r8, rdi; struct tagCHARACTER_RANGE *
0x1800a80d0  mov     edx, r15d; unsigned int
0x1800a80d3  mov     rcx, [rcx+10h]; HRECOCONTEXT
0x1800a80d7  call    ?BackgroundSetEnabledUnicodeRanges@@YAJPEAUHRECOCONTEXT__@@KPEBUtagCHARACTER_RANGE@@P6AJJPEAE@ZPEAX@Z; BackgroundSetEnabledUnicodeRanges(HRECOCONTEXT__ *,ulong,tagCHARACTER_RANGE const *,long (*)(long,uchar *),void *)
0x1800a80dc  mov     ebx, eax
0x1800a80de  test    eax, eax
0x1800a80e0  js      short loc_1800A811D
0x1800a80e2  mov     [rsp+78h+dwindex], 0
0x1800a80ed  lea     r9, [rsi+60h]; pHandles
0x1800a80f1  lea     rax, [rsp+78h+dwindex]
0x1800a80f9  mov     [rsp+78h+lpdwindex], rax; lpdwindex
0x1800a80fe  mov     edx, 493E0h; dwTimeout
0x1800a8103  xor     ecx, ecx; dwFlags
0x1800a8105  lea     r8d, [rcx+1]; cHandles
0x1800a8109  call    cs:__imp_CoWaitForMultipleHandles
0x1800a810f  test    eax, eax
0x1800a8111  mov     ebx, 8000FFFFh
0x1800a8116  js      short loc_1800A812B
0x1800a8118  mov     ebx, [rsi+7Ch]
0x1800a811b  jmp     short loc_1800A812B
0x1800a811d  mov     rcx, r14; pv
0x1800a8120  call    cs:__imp_CoTaskMemFree
0x1800a8126  jmp     short loc_1800A812B
0x1800a8128  mov     ebx, r14d
0x1800a812b  test    rdi, rdi
0x1800a812e  jz      short loc_1800A8139
0x1800a8130  mov     rcx, rdi; void *
0x1800a8133  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x1800a8138  nop
0x1800a8139  jmp     short loc_1800A8142
0x1800a813b  mov     ebx, [rsp+78h+dwindex]
0x1800a8142  lea     rcx, [rsp+78h+var_48]; this
0x1800a8147  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a814c  mov     eax, ebx
0x1800a814e  add     rsp, 40h
0x1800a8152  pop     r15
0x1800a8154  pop     r14
0x1800a8156  pop     r13
0x1800a8158  pop     r12
0x1800a815a  pop     rdi
0x1800a815b  pop     rsi
0x1800a815c  pop     rbx
0x1800a815d  retn
```
