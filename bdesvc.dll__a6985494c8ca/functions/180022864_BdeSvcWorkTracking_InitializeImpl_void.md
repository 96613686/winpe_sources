# BdeSvcWorkTracking::InitializeImpl(void)

- ea: `0x180022864`
- end: `0x180022a13`
- name: `?InitializeImpl@BdeSvcWorkTracking@@AEAAKXZ`
- size: `431`
- prototype: `unsigned int __fastcall(BdeSvcWorkTracking *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180045640`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x180022864`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800228c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022938`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800228c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022938`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800228dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800228dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229a5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002298d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002298d`

## pseudocode

```c
__int64 __fastcall BdeSvcWorkTracking::InitializeImpl(BdeSvcWorkTracking *this)
{
  PVOID *v1; // rcx
  DWORD LastError; // eax
  DWORD v3; // ebx
  __int64 v4; // rdx
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax

  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !hObject )
  {
    hObject = CreateEventW(0, 1, 0, 0);
    if ( !hObject )
    {
      LastError = GetLastError();
      v3 = LastError;
      v1 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v3;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v4 = 11;
        goto LABEL_9;
      }
      goto LABEL_24;
    }
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !hEvent )
  {
    hEvent = CreateEventW(0, 1, 0, 0);
    if ( !hEvent )
    {
      LastError = GetLastError();
      v3 = LastError;
      v1 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v3;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_24;
      v4 = 12;
      goto LABEL_9;
    }
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = 0;
  if ( !qword_18009B940 )
  {
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    qword_18009B940 = (__int64)ThreadpoolCleanupGroup;
    if ( ThreadpoolCleanupGroup )
    {
      pcbe.CleanupGroup = ThreadpoolCleanupGroup;
      pcbe.CleanupGroupCancelCallback = 0;
      goto LABEL_23;
    }
    LastError = GetLastError();
    v3 = LastError;
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_24;
    v4 = 13;
LABEL_9:
    WPP_SF_d(v1[2], v4, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, LastError);
LABEL_23:
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_24:
  if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 0x20) != 0 )
    WPP_SF_(v1[2], 14, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x180022864  mov     [rsp+arg_0], rbx
0x180022869  mov     [rsp+arg_8], rbp
0x18002286e  push    rsi
0x18002286f  sub     rsp, 20h
0x180022873  mov     rcx, cs:WPP_GLOBAL_Control
0x18002287a  lea     rsi, WPP_GLOBAL_Control
0x180022881  lea     rbp, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180022888  cmp     rcx, rsi
0x18002288b  jz      short loc_1800228AB
0x18002288d  test    byte ptr [rcx+1Ch], 20h
0x180022891  jz      short loc_1800228AB
0x180022893  mov     rcx, [rcx+10h]
0x180022897  mov     edx, 0Ah
0x18002289c  mov     r8, rbp
0x18002289f  call    WPP_SF_
0x1800228a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228ab  cmp     cs:hObject, 0
0x1800228b3  mov     ebx, 1
0x1800228b8  jnz     short loc_180022924
0x1800228ba  xor     r9d, r9d; lpName
0x1800228bd  xor     r8d, r8d; bInitialState
0x1800228c0  mov     edx, ebx; bManualReset
0x1800228c2  xor     ecx, ecx; lpEventAttributes
0x1800228c4  call    cs:__imp_CreateEventW
0x1800228cb  nop     dword ptr [rax+rax+00h]
0x1800228d0  mov     cs:hObject, rax
0x1800228d7  test    rax, rax
0x1800228da  jnz     short loc_18002291D
0x1800228dc  call    cs:__imp_GetLastError
0x1800228e3  nop     dword ptr [rax+rax+00h]
0x1800228e8  mov     ebx, eax
0x1800228ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228f1  cmp     rcx, rsi
0x1800228f4  jz      loc_180022A00
0x1800228fa  test    byte ptr [rcx+1Ch], 2
0x1800228fe  jz      loc_1800229E4
0x180022904  mov     edx, 0Bh
0x180022909  mov     rcx, [rcx+10h]
0x18002290d  mov     r9d, eax
0x180022910  mov     r8, rbp
0x180022913  call    WPP_SF_d
0x180022918  jmp     loc_1800229DD
0x18002291d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022924  cmp     cs:hEvent, 0
0x18002292c  jnz     short loc_180022982
0x18002292e  xor     r9d, r9d; lpName
0x180022931  xor     r8d, r8d; bInitialState
0x180022934  mov     edx, ebx; bManualReset
0x180022936  xor     ecx, ecx; lpEventAttributes
0x180022938  call    cs:__imp_CreateEventW
0x18002293f  nop     dword ptr [rax+rax+00h]
0x180022944  mov     cs:hEvent, rax
0x18002294b  test    rax, rax
0x18002294e  jnz     short loc_18002297B
0x180022950  call    cs:__imp_GetLastError
0x180022957  nop     dword ptr [rax+rax+00h]
0x18002295c  mov     ebx, eax
0x18002295e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022965  cmp     rcx, rsi
0x180022968  jz      loc_180022A00
0x18002296e  test    byte ptr [rcx+1Ch], 2
0x180022972  jz      short loc_1800229E4
0x180022974  mov     edx, 0Ch
0x180022979  jmp     short loc_180022909
0x18002297b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022982  xor     ebx, ebx
0x180022984  cmp     cs:qword_18009B940, rbx
0x18002298b  jnz     short loc_1800229E4
0x18002298d  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180022994  nop     dword ptr [rax+rax+00h]
0x180022999  mov     cs:qword_18009B940, rax
0x1800229a0  test    rax, rax
0x1800229a3  jnz     short loc_1800229CF
0x1800229a5  call    cs:__imp_GetLastError
0x1800229ac  nop     dword ptr [rax+rax+00h]
0x1800229b1  mov     ebx, eax
0x1800229b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229ba  cmp     rcx, rsi
0x1800229bd  jz      short loc_180022A00
0x1800229bf  test    byte ptr [rcx+1Ch], 2
0x1800229c3  jz      short loc_1800229E4
0x1800229c5  mov     edx, 0Dh
0x1800229ca  jmp     loc_180022909
0x1800229cf  mov     cs:pcbe.CleanupGroup, rax
0x1800229d6  mov     cs:pcbe.CleanupGroupCancelCallback, rbx
0x1800229dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229e4  cmp     rcx, rsi
0x1800229e7  jz      short loc_180022A00
0x1800229e9  test    byte ptr [rcx+1Ch], 20h
0x1800229ed  jz      short loc_180022A00
0x1800229ef  mov     rcx, [rcx+10h]
0x1800229f3  mov     edx, 0Eh
0x1800229f8  mov     r8, rbp
0x1800229fb  call    WPP_SF_
0x180022a00  mov     rbp, [rsp+28h+arg_8]
0x180022a05  mov     eax, ebx
0x180022a07  mov     rbx, [rsp+28h+arg_0]
0x180022a0c  add     rsp, 20h
0x180022a10  pop     rsi
0x180022a11  retn
```
