# CThreadChasing::Init(void)

- ea: `0x14001d9ec`
- end: `0x14001db1d`
- name: `?Init@CThreadChasing@@QEAAJXZ`
- size: `305`
- prototype: `__int64 __fastcall(CThreadChasing *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140027d70`
- `0x140029bb0`
- `0x140029e40`

## callees

- `0x140014f14`
- `0x14001d9ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001da01`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001da9d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001da01`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001da9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001da38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001dad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001da38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001dad4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001da1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001dabb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001da1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001dabb`

## pseudocode

```c
__int64 __fastcall CThreadChasing::Init(CThreadChasing *this)
{
  HANDLE EventW; // rax
  void *v3; // rcx
  signed int LastError; // eax
  unsigned int v5; // ebx
  CUserModeHangReport *v6; // rcx
  __int64 v7; // rdx
  HANDLE v8; // rax
  void *v9; // rcx
  signed int v10; // eax

  EventW = CreateEventW(0, 1, 0, 0);
  v3 = (void *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = EventW;
  if ( (unsigned __int64)v3 + 1 > 1 )
    CloseHandle(v3);
  if ( *((_QWORD *)this + 1) == -1 || *((_QWORD *)this + 1) == 0 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 14;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v5);
    }
  }
  else
  {
    v8 = CreateEventW(0, 1, 0, 0);
    v9 = (void *)*((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = v8;
    if ( (unsigned __int64)v9 + 1 > 1 )
      CloseHandle(v9);
    if ( *((_QWORD *)this + 2) != -1 && *((_QWORD *)this + 2) != 0 )
      return 0;
    v10 = GetLastError();
    v5 = v10;
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 15;
      goto LABEL_9;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14001d9ec  push    rbx
0x14001d9ee  sub     rsp, 20h
0x14001d9f2  xor     r9d, r9d; lpName
0x14001d9f5  mov     rbx, rcx
0x14001d9f8  xor     r8d, r8d; bInitialState
0x14001d9fb  xor     ecx, ecx; lpEventAttributes
0x14001d9fd  lea     edx, [r9+1]; bManualReset
0x14001da01  call    cs:__imp_CreateEventW
0x14001da08  nop     dword ptr [rax+rax+00h]
0x14001da0d  mov     rcx, [rbx+8]; hObject
0x14001da11  mov     [rbx+8], rax
0x14001da15  lea     rax, [rcx+1]
0x14001da19  cmp     rax, 1
0x14001da1d  jbe     short loc_14001DA2B
0x14001da1f  call    cs:__imp_CloseHandle
0x14001da26  nop     dword ptr [rax+rax+00h]
0x14001da2b  mov     rax, [rbx+8]
0x14001da2f  inc     rax
0x14001da32  cmp     rax, 1
0x14001da36  ja      short loc_14001DA91
0x14001da38  call    cs:__imp_GetLastError
0x14001da3f  nop     dword ptr [rax+rax+00h]
0x14001da44  mov     ebx, eax
0x14001da46  test    eax, eax
0x14001da48  jle     short loc_14001DA53
0x14001da4a  movzx   ebx, ax
0x14001da4d  or      ebx, 80070000h
0x14001da53  mov     rcx, cs:WPP_GLOBAL_Control
0x14001da5a  lea     rax, WPP_GLOBAL_Control
0x14001da61  cmp     rcx, rax
0x14001da64  jz      loc_14001DB14
0x14001da6a  test    byte ptr [rcx+1Ch], 1
0x14001da6e  jz      loc_14001DB14
0x14001da74  mov     edx, 0Eh
0x14001da79  mov     rcx, [rcx+10h]
0x14001da7d  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001da84  mov     r9d, ebx
0x14001da87  call    WPP_SF_d
0x14001da8c  jmp     loc_14001DB14
0x14001da91  xor     r9d, r9d; lpName
0x14001da94  xor     r8d, r8d; bInitialState
0x14001da97  xor     ecx, ecx; lpEventAttributes
0x14001da99  lea     edx, [r9+1]; bManualReset
0x14001da9d  call    cs:__imp_CreateEventW
0x14001daa4  nop     dword ptr [rax+rax+00h]
0x14001daa9  mov     rcx, [rbx+10h]; hObject
0x14001daad  mov     [rbx+10h], rax
0x14001dab1  lea     rax, [rcx+1]
0x14001dab5  cmp     rax, 1
0x14001dab9  jbe     short loc_14001DAC7
0x14001dabb  call    cs:__imp_CloseHandle
0x14001dac2  nop     dword ptr [rax+rax+00h]
0x14001dac7  mov     rax, [rbx+10h]
0x14001dacb  inc     rax
0x14001dace  cmp     rax, 1
0x14001dad2  ja      short loc_14001DB12
0x14001dad4  call    cs:__imp_GetLastError
0x14001dadb  nop     dword ptr [rax+rax+00h]
0x14001dae0  mov     ebx, eax
0x14001dae2  test    eax, eax
0x14001dae4  jle     short loc_14001DAEF
0x14001dae6  movzx   ebx, ax
0x14001dae9  or      ebx, 80070000h
0x14001daef  mov     rcx, cs:WPP_GLOBAL_Control
0x14001daf6  lea     rax, WPP_GLOBAL_Control
0x14001dafd  cmp     rcx, rax
0x14001db00  jz      short loc_14001DB14
0x14001db02  test    byte ptr [rcx+1Ch], 1
0x14001db06  jz      short loc_14001DB14
0x14001db08  mov     edx, 0Fh
0x14001db0d  jmp     loc_14001DA79
0x14001db12  xor     ebx, ebx
0x14001db14  mov     eax, ebx
0x14001db16  add     rsp, 20h
0x14001db1a  pop     rbx
0x14001db1b  retn
```
