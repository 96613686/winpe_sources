# CFveEventLogEvent::RenderValue(ushort const *,_EVT_VARIANT * *)

- ea: `0x180038fdc`
- end: `0x18003927b`
- name: `?RenderValue@CFveEventLogEvent@@AEAAJPEBGPEAPEAU_EVT_VARIANT@@@Z`
- size: `671`
- prototype: `__int64 __fastcall(CFveEventLogEvent *__hidden this, const unsigned __int16 *, struct _EVT_VARIANT **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800320fc`
- `0x180038e10`

## callees

- `0x180009f60`
- `0x180034070`
- `0x180038fdc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039250`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039250`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003912b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003912b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039117`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003923c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039117`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003923c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039035`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039035`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391a2`
- `wevtapi!EvtRender` at `0x1800390b6`
- `wevtapi!EvtRender` at `0x180039192`
- `wevtapi!EvtRender` at `0x1800390b6`
- `wevtapi!EvtRender` at `0x180039192`
- `wevtapi!EvtClose` at `0x18003922b`
- `wevtapi!EvtClose` at `0x18003922b`
- `wevtapi!EvtCreateRenderContext` at `0x180039021`
- `wevtapi!EvtCreateRenderContext` at `0x180039021`

## pseudocode

```c
__int64 __fastcall CFveEventLogEvent::RenderValue(
        EVT_HANDLE *this,
        const unsigned __int16 *a2,
        struct _EVT_VARIANT **a3)
{
  EVT_HANDLE v5; // r12
  signed int LastError; // eax
  unsigned int v7; // ebx
  struct _EVT_VARIANT *v8; // rsi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  SIZE_T v11; // rbp
  HANDLE ProcessHeap; // rax
  struct _EVT_VARIANT *Buffer; // rdi
  signed int v14; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  HANDLE v17; // rax
  LPCWSTR ValuePaths; // [rsp+40h] [rbp-58h] BYREF
  DWORD BufferSize; // [rsp+48h] [rbp-50h] BYREF
  DWORD PropertyCount; // [rsp+4Ch] [rbp-4Ch] BYREF

  ValuePaths = a2;
  BufferSize = 0;
  PropertyCount = 0;
  v5 = EvtCreateRenderContext(1u, &ValuePaths, 0);
  if ( !v5 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_be435f8e4c0535904aa1fb6c51ba2d0f_Traceguids, v7);
    return v7;
  }
  v8 = 0;
  if ( EvtRender(v5, this[1], 0, 0, 0, &BufferSize, &PropertyCount) )
  {
    v7 = -2147467259;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v10 = 21;
LABEL_11:
      WPP_SF_d(v9[2], v10, WPP_be435f8e4c0535904aa1fb6c51ba2d0f_Traceguids, v7);
      goto LABEL_33;
    }
    goto LABEL_33;
  }
  v11 = BufferSize;
  if ( BufferSize >= 0x10 )
  {
    ProcessHeap = GetProcessHeap();
    Buffer = (struct _EVT_VARIANT *)HeapAlloc(ProcessHeap, 0, v11);
    if ( !Buffer )
    {
      v7 = -2147024882;
      goto LABEL_16;
    }
    if ( EvtRender(v5, this[1], 0, v11, Buffer, &BufferSize, &PropertyCount) )
    {
      if ( PropertyCount && Buffer->Type )
      {
        *a3 = Buffer;
        v7 = 0;
        goto LABEL_33;
      }
      v7 = -2147023728;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_32;
      v16 = 24;
    }
    else
    {
      v14 = GetLastError();
      v7 = v14;
      if ( v14 > 0 )
        v7 = (unsigned __int16)v14 | 0x80070000;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_32;
      v16 = 23;
    }
    WPP_SF_d(v15[2], v16, WPP_be435f8e4c0535904aa1fb6c51ba2d0f_Traceguids, v7);
LABEL_32:
    v8 = Buffer;
    goto LABEL_33;
  }
  v7 = -2147024809;
LABEL_16:
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v10 = 22;
    goto LABEL_11;
  }
LABEL_33:
  EvtClose(v5);
  if ( v8 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v8);
  }
  return v7;
}

```

## disassembly

```asm
0x180038fdc  push    rbx
0x180038fde  push    rbp
0x180038fdf  push    rsi
0x180038fe0  push    rdi
0x180038fe1  push    r12
0x180038fe3  push    r14
0x180038fe5  push    r15
0x180038fe7  sub     rsp, 60h
0x180038feb  mov     rax, cs:__security_cookie
0x180038ff2  xor     rax, rsp
0x180038ff5  mov     [rsp+98h+var_48], rax
0x180038ffa  mov     r15, r8
0x180038ffd  mov     [rsp+98h+ValuePaths], rdx
0x180039002  xor     r8d, r8d; Flags
0x180039005  mov     [rsp+98h+BufferSize], 0
0x18003900d  mov     r14, rcx
0x180039010  mov     [rsp+98h+var_4C], 0
0x180039018  lea     rdx, [rsp+98h+ValuePaths]; ValuePaths
0x18003901d  lea     ecx, [r8+1]; ValuePathsCount
0x180039021  call    cs:__imp_EvtCreateRenderContext
0x180039028  nop     dword ptr [rax+rax+00h]
0x18003902d  mov     r12, rax
0x180039030  test    rax, rax
0x180039033  jnz     short loc_18003908E
0x180039035  call    cs:__imp_GetLastError
0x18003903c  nop     dword ptr [rax+rax+00h]
0x180039041  mov     ebx, eax
0x180039043  test    eax, eax
0x180039045  jle     short loc_180039050
0x180039047  movzx   ebx, ax
0x18003904a  or      ebx, 80070000h
0x180039050  mov     rcx, cs:WPP_GLOBAL_Control
0x180039057  lea     rax, WPP_GLOBAL_Control
0x18003905e  cmp     rcx, rax
0x180039061  jz      loc_18003925C
0x180039067  test    byte ptr [rcx+1Ch], 40h
0x18003906b  jz      loc_18003925C
0x180039071  mov     rcx, [rcx+10h]
0x180039075  lea     r8, WPP_be435f8e4c0535904aa1fb6c51ba2d0f_Traceguids
0x18003907c  mov     edx, 14h
0x180039081  mov     r9d, ebx
0x180039084  call    WPP_SF_d
0x180039089  jmp     loc_18003925C
0x18003908e  mov     rdx, [r14+8]; Fragment
0x180039092  lea     rax, [rsp+98h+var_4C]
0x180039097  mov     [rsp+98h+PropertyCount], rax; PropertyCount
0x18003909c  xor     esi, esi
0x18003909e  lea     rax, [rsp+98h+BufferSize]
0x1800390a3  xor     r9d, r9d; BufferSize
0x1800390a6  mov     [rsp+98h+BufferUsed], rax; BufferUsed
0x1800390ab  xor     r8d, r8d; Flags
0x1800390ae  mov     rcx, r12; Context
0x1800390b1  mov     [rsp+98h+Buffer], rsi; Buffer
0x1800390b6  call    cs:__imp_EvtRender
0x1800390bd  nop     dword ptr [rax+rax+00h]
0x1800390c2  test    eax, eax
0x1800390c4  jz      short loc_180039107
0x1800390c6  mov     ebx, 80004005h
0x1800390cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800390d2  lea     rax, WPP_GLOBAL_Control
0x1800390d9  cmp     rcx, rax
0x1800390dc  jz      loc_180039228
0x1800390e2  test    byte ptr [rcx+1Ch], 40h
0x1800390e6  jz      loc_180039228
0x1800390ec  lea     edx, [rsi+15h]
0x1800390ef  mov     rcx, [rcx+10h]
0x1800390f3  lea     r8, WPP_be435f8e4c0535904aa1fb6c51ba2d0f_Traceguids
0x1800390fa  mov     r9d, ebx
0x1800390fd  call    WPP_SF_d
0x180039102  jmp     loc_180039228
0x180039107  mov     ebp, [rsp+98h+BufferSize]
0x18003910b  cmp     ebp, 10h
0x18003910e  jnb     short loc_180039117
0x180039110  mov     ebx, 80070057h
0x180039115  jmp     short loc_180039144
0x180039117  call    cs:__imp_GetProcessHeap
0x18003911e  nop     dword ptr [rax+rax+00h]
0x180039123  mov     r8, rbp; dwBytes
0x180039126  xor     edx, edx; dwFlags
0x180039128  mov     rcx, rax; hHeap
0x18003912b  call    cs:__imp_HeapAlloc
0x180039132  nop     dword ptr [rax+rax+00h]
0x180039137  mov     rdi, rax
0x18003913a  test    rax, rax
0x18003913d  jnz     short loc_18003916C
0x18003913f  mov     ebx, 8007000Eh
0x180039144  mov     rcx, cs:WPP_GLOBAL_Control
0x18003914b  lea     rax, WPP_GLOBAL_Control
0x180039152  cmp     rcx, rax
0x180039155  jz      loc_180039228
0x18003915b  test    byte ptr [rcx+1Ch], 40h
0x18003915f  jz      loc_180039228
0x180039165  mov     edx, 16h
0x18003916a  jmp     short loc_1800390EF
0x18003916c  mov     rdx, [r14+8]; Fragment
0x180039170  lea     rax, [rsp+98h+var_4C]
0x180039175  mov     [rsp+98h+PropertyCount], rax; PropertyCount
0x18003917a  mov     r9d, ebp; BufferSize
0x18003917d  lea     rax, [rsp+98h+BufferSize]
0x180039182  xor     r8d, r8d; Flags
0x180039185  mov     [rsp+98h+BufferUsed], rax; BufferUsed
0x18003918a  mov     rcx, r12; Context
0x18003918d  mov     [rsp+98h+Buffer], rdi; Buffer
0x180039192  call    cs:__imp_EvtRender
0x180039199  nop     dword ptr [rax+rax+00h]
0x18003919e  test    eax, eax
0x1800391a0  jnz     short loc_1800391DD
0x1800391a2  call    cs:__imp_GetLastError
0x1800391a9  nop     dword ptr [rax+rax+00h]
0x1800391ae  mov     ebx, eax
0x1800391b0  test    eax, eax
0x1800391b2  jle     short loc_1800391BD
0x1800391b4  movzx   ebx, ax
0x1800391b7  or      ebx, 80070000h
0x1800391bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800391c4  lea     rax, WPP_GLOBAL_Control
0x1800391cb  cmp     rcx, rax
0x1800391ce  jz      short loc_180039225
0x1800391d0  test    byte ptr [rcx+1Ch], 40h
0x1800391d4  jz      short loc_180039225
0x1800391d6  mov     edx, 17h
0x1800391db  jmp     short loc_180039212
0x1800391dd  cmp     [rsp+98h+var_4C], esi
0x1800391e1  jz      short loc_1800391EF
0x1800391e3  cmp     [rdi+0Ch], esi
0x1800391e6  jz      short loc_1800391EF
0x1800391e8  mov     [r15], rdi
0x1800391eb  xor     ebx, ebx
0x1800391ed  jmp     short loc_180039228
0x1800391ef  mov     ebx, 80070490h
0x1800391f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800391fb  lea     rax, WPP_GLOBAL_Control
0x180039202  cmp     rcx, rax
0x180039205  jz      short loc_180039225
0x180039207  test    byte ptr [rcx+1Ch], 40h
0x18003920b  jz      short loc_180039225
0x18003920d  mov     edx, 18h
0x180039212  mov     rcx, [rcx+10h]
0x180039216  lea     r8, WPP_be435f8e4c0535904aa1fb6c51ba2d0f_Traceguids
0x18003921d  mov     r9d, ebx
0x180039220  call    WPP_SF_d
0x180039225  mov     rsi, rdi
0x180039228  mov     rcx, r12; Object
0x18003922b  call    cs:__imp_EvtClose
0x180039232  nop     dword ptr [rax+rax+00h]
0x180039237  test    rsi, rsi
0x18003923a  jz      short loc_18003925C
0x18003923c  call    cs:__imp_GetProcessHeap
0x180039243  nop     dword ptr [rax+rax+00h]
0x180039248  mov     r8, rsi; lpMem
0x18003924b  xor     edx, edx; dwFlags
0x18003924d  mov     rcx, rax; hHeap
0x180039250  call    cs:__imp_HeapFree
0x180039257  nop     dword ptr [rax+rax+00h]
0x18003925c  mov     eax, ebx
0x18003925e  mov     rcx, [rsp+98h+var_48]
0x180039263  xor     rcx, rsp; StackCookie
0x180039266  call    __security_check_cookie
0x18003926b  add     rsp, 60h
0x18003926f  pop     r15
0x180039271  pop     r14
0x180039273  pop     r12
0x180039275  pop     rdi
0x180039276  pop     rsi
0x180039277  pop     rbp
0x180039278  pop     rbx
0x180039279  retn
```
