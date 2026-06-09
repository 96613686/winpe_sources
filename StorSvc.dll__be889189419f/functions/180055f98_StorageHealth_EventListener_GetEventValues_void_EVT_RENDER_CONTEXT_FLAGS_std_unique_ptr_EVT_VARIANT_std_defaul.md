# StorageHealth::EventListener::GetEventValues(void *,_EVT_RENDER_CONTEXT_FLAGS,std::unique_ptr<_EVT_VARIANT,std::default_delete<_EVT_VARIANT>> &,ulong &)

- ea: `0x180055f98`
- end: `0x18005612e`
- name: `?GetEventValues@EventListener@StorageHealth@@QEAAJPEAXW4_EVT_RENDER_CONTEXT_FLAGS@@AEAV?$unique_ptr@U_EVT_VARIANT@@U?$default_delete@U_EVT_VARIANT@@@std@@@std@@AEAK@Z`
- size: `406`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18004e634`
- `0x180055cc4`
- `0x180058f24`
- `0x18005dc0c`

## callees

- `0x18000d400`
- `0x18000dbd0`
- `0x180012734`
- `0x180055f98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800560a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800560a6`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x180056036`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x18005609c`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x180056036`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x18005609c`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x1800560e9`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x1800560e9`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x180055fc9`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x180055fc9`

## pseudocode

```c
__int64 __fastcall StorageHealth::EventListener::GetEventValues(
        __int64 a1,
        void *a2,
        DWORD a3,
        void **a4,
        PDWORD PropertyCount)
{
  void **v5; // r14
  EVT_HANDLE RenderContext; // rsi
  signed int v8; // ebx
  void *v9; // rdi
  DWORD *v10; // r13
  signed int LastError; // eax
  DWORD v12; // r15d
  unsigned __int64 v13; // rax
  signed int v14; // eax
  const struct std::nothrow_t *v15; // rdx
  void *v16; // rcx
  int Buffer; // [rsp+20h] [rbp-68h]
  void *v19; // [rsp+48h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  DWORD BufferSize; // [rsp+90h] [rbp+8h] BYREF
  int v22; // [rsp+94h] [rbp+Ch]
  void **v23; // [rsp+A8h] [rbp+20h]

  v23 = a4;
  v22 = HIDWORD(a1);
  v5 = a4;
  BufferSize = 0;
  RenderContext = EvtCreateRenderContext(0, 0, a3);
  if ( RenderContext )
  {
    v8 = 0;
    v9 = 0;
    v10 = PropertyCount;
    if ( !EvtRender(RenderContext, a2, 0, 0, 0, &BufferSize, PropertyCount) )
    {
      LastError = GetLastError();
      if ( LastError == 122 )
      {
        v12 = BufferSize;
        v13 = 16LL * BufferSize;
        if ( !is_mul_ok(BufferSize, 0x10u) )
          v13 = -1;
        try
        {
          v9 = operator new[](v13);
          v19 = v9;
          if ( !EvtRender(RenderContext, a2, 0, v12, v9, &BufferSize, v10) )
          {
            v14 = GetLastError();
            v8 = v14;
            if ( v14 > 0 )
              v8 = (unsigned __int16)v14 | 0x80070000;
          }
        }
        catch ( std::bad_alloc )
        {
          v5 = v23;
          v8 = -2147024882;
          v9 = v19;
        }
      }
      else if ( LastError > 0 )
      {
        v8 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v8 = LastError;
      }
    }
    EvtClose(RenderContext);
    if ( v8 >= 0 )
    {
      v16 = *v5;
      *v5 = v9;
      if ( v16 )
        operator delete(v16, (const struct std::nothrow_t *)0x10);
    }
    else
    {
      operator delete(v9, v15);
    }
  }
  else
  {
    v8 = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x107,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagehealth\\eventlistener.cpp",
      (const char *)0x80004005LL,
      Buffer);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180055f98  mov     rax, rsp
0x180055f9b  mov     [rax+10h], rbx
0x180055f9f  mov     [rax+18h], rsi
0x180055fa3  mov     [rax+20h], r9
0x180055fa7  mov     [rax+8], rcx
0x180055fab  push    rdi
0x180055fac  push    r12
0x180055fae  push    r13
0x180055fb0  push    r14
0x180055fb2  push    r15
0x180055fb4  sub     rsp, 60h
0x180055fb8  mov     r14, r9
0x180055fbb  mov     r12, rdx
0x180055fbe  mov     dword ptr [rax+8], 0
0x180055fc5  xor     edx, edx; ValuePaths
0x180055fc7  xor     ecx, ecx; ValuePathsCount
0x180055fc9  call    cs:__imp_EvtCreateRenderContext
0x180055fcf  mov     rsi, rax
0x180055fd2  mov     [rsp+88h+var_38], rax
0x180055fd7  test    rax, rax
0x180055fda  jnz     short loc_180056002
0x180055fdc  mov     rcx, [rsp+88h]; this
0x180055fe4  mov     ebx, 80004005h
0x180055fe9  mov     r9d, ebx; char *
0x180055fec  lea     r8, aOnecoreDrivers_17; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180055ff3  mov     edx, 107h; void *
0x180055ff8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055ffd  jmp     loc_180056112
0x180056002  xor     ebx, ebx
0x180056004  xor     edi, edi
0x180056006  mov     [rsp+88h+var_40], rdi
0x18005600b  mov     r13, [rsp+88h+arg_20]
0x180056013  mov     [rsp+88h+PropertyCount], r13; PropertyCount
0x180056018  lea     rax, [rsp+88h+BufferSize]
0x180056020  mov     [rsp+88h+BufferUsed], rax; BufferUsed
0x180056025  mov     [rsp+88h+Buffer], rbx; Buffer
0x18005602a  xor     r9d, r9d; BufferSize
0x18005602d  xor     r8d, r8d; Flags
0x180056030  mov     rdx, r12; Fragment
0x180056033  mov     rcx, rsi; Context
0x180056036  call    cs:__imp_EvtRender
0x18005603c  test    eax, eax
0x18005603e  jnz     loc_1800560E6
0x180056044  call    cs:__imp_GetLastError
0x18005604a  cmp     eax, 7Ah ; 'z'
0x18005604d  jnz     loc_1800560D5
0x180056053  mov     r15d, [rsp+88h+BufferSize]
0x18005605b  lea     eax, [rbx+10h]
0x18005605e  mul     r15
0x180056061  lea     rcx, [rbx-1]
0x180056065  cmovb   rax, rcx
0x180056069  mov     rcx, rax; unsigned __int64
0x18005606c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180056071  mov     rdi, rax
0x180056074  mov     [rsp+88h+var_40], rax
0x180056079  mov     [rsp+88h+PropertyCount], r13; PropertyCount
0x18005607e  lea     rax, [rsp+88h+BufferSize]
0x180056086  mov     [rsp+88h+BufferUsed], rax; BufferUsed
0x18005608b  mov     [rsp+88h+Buffer], rdi; Buffer
0x180056090  mov     r9d, r15d; BufferSize
0x180056093  xor     r8d, r8d; Flags
0x180056096  mov     rdx, r12; Fragment
0x180056099  mov     rcx, rsi; Context
0x18005609c  call    cs:__imp_EvtRender
0x1800560a2  test    eax, eax
0x1800560a4  jnz     short loc_1800560BB
0x1800560a6  call    cs:__imp_GetLastError
0x1800560ac  mov     ebx, eax
0x1800560ae  test    eax, eax
0x1800560b0  jle     short loc_1800560BB
0x1800560b2  movzx   ebx, ax
0x1800560b5  or      ebx, 80070000h
0x1800560bb  jmp     short loc_1800560E6
0x1800560bd  mov     r14, [rsp+88h+arg_18]
0x1800560c5  mov     ebx, [rsp+88h+var_48]
0x1800560c9  mov     rsi, [rsp+88h+var_38]
0x1800560ce  mov     rdi, [rsp+88h+var_40]
0x1800560d3  jmp     short loc_1800560E6
0x1800560d5  test    eax, eax
0x1800560d7  jg      short loc_1800560DD
0x1800560d9  mov     ebx, eax
0x1800560db  jmp     short loc_1800560E6
0x1800560dd  movzx   ebx, ax
0x1800560e0  or      ebx, 80070000h
0x1800560e6  mov     rcx, rsi; Object
0x1800560e9  call    cs:__imp_EvtClose
0x1800560ef  test    ebx, ebx
0x1800560f1  jns     short loc_1800560FD
0x1800560f3  mov     rcx, rdi; void *
0x1800560f6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800560fb  jmp     short loc_180056112
0x1800560fd  mov     rcx, [r14]; void *
0x180056100  mov     [r14], rdi
0x180056103  test    rcx, rcx
0x180056106  jz      short loc_180056112
0x180056108  mov     edx, 10h; struct std::nothrow_t *
0x18005610d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180056112  mov     eax, ebx
0x180056114  lea     r11, [rsp+88h+var_28]
0x180056119  mov     rbx, [r11+38h]
0x18005611d  mov     rsi, [r11+40h]
0x180056121  mov     rsp, r11
0x180056124  pop     r15
0x180056126  pop     r14
0x180056128  pop     r13
0x18005612a  pop     r12
0x18005612c  pop     rdi
0x18005612d  retn
```
