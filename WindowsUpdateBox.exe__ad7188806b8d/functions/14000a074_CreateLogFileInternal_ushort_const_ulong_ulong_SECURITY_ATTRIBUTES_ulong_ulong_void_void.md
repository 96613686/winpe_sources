# CreateLogFileInternal(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,void * *)

- ea: `0x14000a074`
- end: `0x14000a214`
- name: `?CreateLogFileInternal@@YAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEAPEAX@Z`
- size: `416`
- prototype: `__int64 __fastcall(const unsigned __int16 *, DWORD, DWORD, struct _SECURITY_ATTRIBUTES *, DWORD dwCreationDisposition, unsigned int, void *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140007dd4`
- `0x140021744`

## callees

- `0x1400076c8`
- `0x140007cb0`
- `0x14000a074`
- `0x1400135b8`
- `0x140016a58`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000a1b8`
- `KERNEL32!HeapFree` at `0x14000a1e5`
- `KERNEL32!HeapFree` at `0x14000a1b8`
- `KERNEL32!HeapFree` at `0x14000a1e5`
- `KERNEL32!GetProcessHeap` at `0x14000a1a3`
- `KERNEL32!GetProcessHeap` at `0x14000a1d0`
- `KERNEL32!GetProcessHeap` at `0x14000a1a3`
- `KERNEL32!GetProcessHeap` at `0x14000a1d0`
- `KERNEL32!GetLastError` at `0x14000a15c`
- `KERNEL32!GetLastError` at `0x14000a15c`
- `KERNEL32!CreateFileW` at `0x14000a140`
- `KERNEL32!CreateFileW` at `0x14000a140`

## pseudocode

```c
__int64 __fastcall CreateLogFileInternal(
        const unsigned __int16 *a1,
        DWORD a2,
        DWORD a3,
        struct _SECURITY_ATTRIBUTES *a4,
        DWORD dwCreationDisposition,
        unsigned int a6,
        void *a7,
        void **a8)
{
  unsigned __int16 *v8; // rsi
  unsigned int v12; // edi
  int v13; // eax
  int v14; // eax
  HANDLE FileW; // rdx
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v19; // [rsp+88h] [rbp+20h] BYREF

  v8 = 0;
  v19 = 0;
  if ( !a1 )
  {
    v12 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
    goto LABEL_14;
  }
  v13 = OpenLogFolder(&v19);
  v12 = v13;
  if ( v13 >= 0 )
  {
    v8 = v19;
    v14 = CMiscHelpersT<CEmptyType>::CombinePath((__int64)v19, (__int64)a1, 0);
    v12 = v14;
    if ( v14 >= 0 )
    {
      FileW = CreateFileW(0, a2, a3, 0, dwCreationDisposition, 0x80u, 0);
      if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError )
        {
          if ( LastError > 0 )
            v12 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v12 = -2147467259;
        }
        goto LABEL_3;
      }
      *a8 = FileW;
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v14);
    }
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
    v8 = v19;
  }
LABEL_14:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v12;
}

```

## disassembly

```asm
0x14000a074  mov     rax, rsp
0x14000a077  mov     [rax+10h], rbx
0x14000a07b  mov     [rax+18h], rbp
0x14000a07f  mov     [rax+20h], r9
0x14000a083  push    rsi
0x14000a084  push    rdi
0x14000a085  push    r12
0x14000a087  push    r14
0x14000a089  push    r15
0x14000a08b  sub     rsp, 40h
0x14000a08f  xor     esi, esi
0x14000a091  xor     ebp, ebp
0x14000a093  mov     [rax+20h], rsi
0x14000a097  mov     r15d, r8d
0x14000a09a  mov     [rax+8], rbp
0x14000a09e  mov     r12d, edx
0x14000a0a1  mov     r14, rcx
0x14000a0a4  test    rcx, rcx
0x14000a0a7  jnz     short loc_14000A0BA
0x14000a0a9  mov     edi, 80070057h
0x14000a0ae  mov     ecx, edi
0x14000a0b0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000a0b5  jmp     loc_14000A197
0x14000a0ba  lea     rcx, [rsp+68h+arg_18]; unsigned __int16 **
0x14000a0c2  call    ?OpenLogFolder@@YAJPEAPEAG@Z; OpenLogFolder(ushort * *)
0x14000a0c7  mov     edi, eax
0x14000a0c9  test    eax, eax
0x14000a0cb  jns     short loc_14000A0E1
0x14000a0cd  mov     ecx, eax
0x14000a0cf  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000a0d4  mov     rsi, [rsp+68h+arg_18]
0x14000a0dc  jmp     loc_14000A197
0x14000a0e1  mov     rsi, [rsp+68h+arg_18]
0x14000a0e9  lea     r9, [rsp+68h+lpFileName]
0x14000a0ee  mov     rcx, rsi
0x14000a0f1  xor     r8d, r8d
0x14000a0f4  mov     rdx, r14
0x14000a0f7  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x14000a0fc  mov     edi, eax
0x14000a0fe  test    eax, eax
0x14000a100  jns     short loc_14000A113
0x14000a102  mov     ecx, eax
0x14000a104  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000a109  mov     rbp, [rsp+68h+lpFileName]
0x14000a10e  jmp     loc_14000A197
0x14000a113  mov     eax, [rsp+68h+arg_20]
0x14000a11a  xor     r9d, r9d; lpSecurityAttributes
0x14000a11d  mov     rbp, [rsp+68h+lpFileName]
0x14000a122  mov     r8d, r15d; dwShareMode
0x14000a125  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x14000a12e  mov     rcx, rbp; lpFileName
0x14000a131  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000a139  mov     edx, r12d; dwDesiredAccess
0x14000a13c  mov     [rsp+68h+dwCreationDisposition], eax; dwCreationDisposition
0x14000a140  call    cs:__imp_CreateFileW
0x14000a147  nop     dword ptr [rax+rax+00h]
0x14000a14c  mov     rdx, rax
0x14000a14f  lea     rcx, [rax+1]
0x14000a153  test    rcx, 0FFFFFFFFFFFFFFFEh
0x14000a15a  jnz     short loc_14000A18C
0x14000a15c  call    cs:__imp_GetLastError
0x14000a163  nop     dword ptr [rax+rax+00h]
0x14000a168  mov     edi, eax
0x14000a16a  test    eax, eax
0x14000a16c  jnz     short loc_14000A178
0x14000a16e  mov     edi, 80004005h
0x14000a173  jmp     loc_14000A0AE
0x14000a178  jle     loc_14000A0AE
0x14000a17e  movzx   edi, ax
0x14000a181  or      edi, 80070000h
0x14000a187  jmp     loc_14000A0AE
0x14000a18c  mov     rax, [rsp+68h+arg_38]
0x14000a194  mov     [rax], rdx
0x14000a197  mov     ecx, edi
0x14000a199  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000a19e  test    rbp, rbp
0x14000a1a1  jz      short loc_14000A1CB
0x14000a1a3  call    cs:__imp_GetProcessHeap
0x14000a1aa  nop     dword ptr [rax+rax+00h]
0x14000a1af  lea     r8, [rbp-4]; lpMem
0x14000a1b3  xor     edx, edx; dwFlags
0x14000a1b5  mov     rcx, rax; hHeap
0x14000a1b8  call    cs:__imp_HeapFree
0x14000a1bf  nop     dword ptr [rax+rax+00h]
0x14000a1c4  xor     ecx, ecx
0x14000a1c6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000a1cb  test    rsi, rsi
0x14000a1ce  jz      short loc_14000A1F8
0x14000a1d0  call    cs:__imp_GetProcessHeap
0x14000a1d7  nop     dword ptr [rax+rax+00h]
0x14000a1dc  lea     r8, [rsi-4]; lpMem
0x14000a1e0  xor     edx, edx; dwFlags
0x14000a1e2  mov     rcx, rax; hHeap
0x14000a1e5  call    cs:__imp_HeapFree
0x14000a1ec  nop     dword ptr [rax+rax+00h]
0x14000a1f1  xor     ecx, ecx
0x14000a1f3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000a1f8  lea     r11, [rsp+68h+var_28]
0x14000a1fd  mov     eax, edi
0x14000a1ff  mov     rbx, [r11+38h]
0x14000a203  mov     rbp, [r11+40h]
0x14000a207  mov     rsp, r11
0x14000a20a  pop     r15
0x14000a20c  pop     r14
0x14000a20e  pop     r12
0x14000a210  pop     rdi
0x14000a211  pop     rsi
0x14000a212  retn
```
