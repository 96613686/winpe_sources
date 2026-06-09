# ipx::mtf::CMtfSuggestionClient::UnadviseLatticeNotifySink(IMtfSuggestionLatticeNotify *)

- ea: `0x18001c680`
- end: `0x18001c75f`
- name: `?UnadviseLatticeNotifySink@CMtfSuggestionClient@mtf@ipx@@UEAAJPEAUIMtfSuggestionLatticeNotify@@@Z`
- size: `223`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfSuggestionClient *__hidden this, struct IMtfSuggestionLatticeNotify *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006074`
- `0x18001048c`
- `0x18001c680`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c746`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c746`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c6cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c6cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c696`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c696`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::UnadviseLatticeNotifySink(
        ipx::mtf::CMtfSuggestionClient *this,
        struct IMtfSuggestionLatticeNotify *a2)
{
  int v4; // ebx
  int v6; // edx
  struct IMtfSuggestionLatticeNotify *v7; // rcx
  unsigned int v8; // ebx
  int v9; // r9d
  const char *v10; // r9
  int v11; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = *((_DWORD *)this + 50);
  if ( v4 != GetCurrentThreadId() )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F2,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)0x8001010ELL,
      v11);
    return 2147549454LL;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v7 = (struct IMtfSuggestionLatticeNotify *)*((_QWORD *)this + 16);
  if ( v7 )
  {
    if ( v7 == a2 )
    {
      try
      {
        v8 = 0;
        *((_QWORD *)this + 16) = 0;
        (*(void (__fastcall **)(struct IMtfSuggestionLatticeNotify *))(*(_QWORD *)v7 + 16LL))(v7);
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x401,
                               (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                               v10);
      }
      goto LABEL_10;
    }
    v8 = -2147024809;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
    {
      v9 = 1018;
      goto LABEL_6;
    }
  }
  else
  {
    v8 = -2147024809;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
    {
      v9 = 1017;
LABEL_6:
      McTemplateU0sqq_EventWriteTransfer(
        (_DWORD)v7,
        v6,
        (unsigned int)"ipx::mtf::CMtfSuggestionClient::UnadviseLatticeNotifySink",
        v9,
        87);
    }
  }
LABEL_10:
  if ( this != (ipx::mtf::CMtfSuggestionClient *)-64LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return v8;
}

```

## disassembly

```asm
0x18001c680  push    rbx
0x18001c682  push    rsi
0x18001c683  push    rdi
0x18001c684  push    r14
0x18001c686  sub     rsp, 38h
0x18001c68a  mov     r14, rdx
0x18001c68d  mov     rsi, rcx
0x18001c690  mov     ebx, [rcx+0C8h]
0x18001c696  call    cs:__imp_GetCurrentThreadId
0x18001c69c  cmp     ebx, eax
0x18001c69e  jz      short loc_18001C6C5
0x18001c6a0  mov     rcx, [rsp+58h]; this
0x18001c6a5  mov     ebx, 8001010Eh
0x18001c6aa  mov     r9d, ebx; char *
0x18001c6ad  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001c6b4  mov     edx, 3F2h; void *
0x18001c6b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c6be  mov     eax, ebx
0x18001c6c0  jmp     loc_18001C754
0x18001c6c5  lea     rdi, [rsi+40h]
0x18001c6c9  mov     rcx, rdi; lpCriticalSection
0x18001c6cc  call    cs:__imp_EnterCriticalSection
0x18001c6d2  mov     [rsp+58h+arg_0], rdi
0x18001c6d7  mov     rcx, [rsi+80h]
0x18001c6de  test    rcx, rcx
0x18001c6e1  jnz     short loc_18001C70D
0x18001c6e3  mov     ebx, 80070057h
0x18001c6e8  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18001c6ef  jz      short loc_18001C73E
0x18001c6f1  mov     r9d, 3F9h
0x18001c6f7  mov     [rsp+58h+var_38], 80070057h
0x18001c6ff  lea     r8, aIpxMtfCmtfsugg; "ipx::mtf::CMtfSuggestionClient::Unadvis"...
0x18001c706  call    McTemplateU0sqq_EventWriteTransfer
0x18001c70b  jmp     short loc_18001C73E
0x18001c70d  cmp     rcx, r14
0x18001c710  jz      short loc_18001C728
0x18001c712  mov     ebx, 80070057h
0x18001c717  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18001c71e  jz      short loc_18001C73E
0x18001c720  mov     r9d, 3FAh
0x18001c726  jmp     short loc_18001C6F7
0x18001c728  xor     ebx, ebx
0x18001c72a  mov     [rsi+80h], rbx
0x18001c731  mov     rax, [rcx]
0x18001c734  mov     rax, [rax+10h]
0x18001c738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c73d  nop
0x18001c73e  test    rdi, rdi
0x18001c741  jz      short loc_18001C74C
0x18001c743  mov     rcx, rdi; lpCriticalSection
0x18001c746  call    cs:__imp_LeaveCriticalSection
0x18001c74c  mov     eax, ebx
0x18001c74e  jmp     short loc_18001C754
0x18001c750  mov     eax, dword ptr [rsp+58h+arg_0]
0x18001c754  add     rsp, 38h
0x18001c758  pop     r14
0x18001c75a  pop     rdi
0x18001c75b  pop     rsi
0x18001c75c  pop     rbx
0x18001c75d  retn
```
