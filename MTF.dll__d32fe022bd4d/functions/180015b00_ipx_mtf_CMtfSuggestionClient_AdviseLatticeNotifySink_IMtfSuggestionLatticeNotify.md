# ipx::mtf::CMtfSuggestionClient::AdviseLatticeNotifySink(IMtfSuggestionLatticeNotify *)

- ea: `0x180015b00`
- end: `0x180015bf4`
- name: `?AdviseLatticeNotifySink@CMtfSuggestionClient@mtf@ipx@@UEAAJPEAUIMtfSuggestionLatticeNotify@@@Z`
- size: `244`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfSuggestionClient *__hidden this, struct IMtfSuggestionLatticeNotify *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006074`
- `0x18001048c`
- `0x180015b00`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015bd5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015bd5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015b51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015b51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015b1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015b1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::AdviseLatticeNotifySink(
        ipx::mtf::CMtfSuggestionClient *this,
        struct IMtfSuggestionLatticeNotify *a2)
{
  int v4; // ebx
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  int v7; // edx
  int v8; // ecx
  unsigned int v9; // edi
  int v10; // r9d
  const char *v11; // r9
  int v12; // [rsp+20h] [rbp-18h]
  char v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = *((_DWORD *)this + 50);
  if ( v4 != GetCurrentThreadId() )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D1,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)0x8001010ELL,
      v12);
    return 2147549454LL;
  }
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( a2 )
  {
    if ( !*((_QWORD *)this + 16) )
    {
      try
      {
        v9 = (**(__int64 (__fastcall ***)(struct IMtfSuggestionLatticeNotify *, GUID *))a2)(
               a2,
               &IID_IMtfSuggestionLatticeNotify);
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x3E0,
                               (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                               v11);
      }
      goto LABEL_10;
    }
    v9 = -2147418113;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
    {
      v13 = -1;
      v10 = 985;
      goto LABEL_6;
    }
  }
  else
  {
    v9 = -2147024809;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
    {
      v13 = 87;
      v10 = 983;
LABEL_6:
      McTemplateU0sqq_EventWriteTransfer(
        v8,
        v7,
        (unsigned int)"ipx::mtf::CMtfSuggestionClient::AdviseLatticeNotifySink",
        v10,
        v13);
    }
  }
LABEL_10:
  if ( v6 )
    LeaveCriticalSection(v6);
  return v9;
}

```

## disassembly

```asm
0x180015b00  mov     [rsp+arg_8], rbx
0x180015b05  mov     [rsp+arg_10], rsi
0x180015b0a  push    rdi
0x180015b0b  sub     rsp, 30h
0x180015b0f  mov     rsi, rdx
0x180015b12  mov     rdi, rcx
0x180015b15  mov     ebx, [rcx+0C8h]
0x180015b1b  call    cs:__imp_GetCurrentThreadId
0x180015b21  cmp     ebx, eax
0x180015b23  jz      short loc_180015B4A
0x180015b25  mov     rcx, [rsp+38h]; this
0x180015b2a  mov     ebx, 8001010Eh
0x180015b2f  mov     r9d, ebx; char *
0x180015b32  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180015b39  mov     edx, 3D1h; void *
0x180015b3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015b43  mov     eax, ebx
0x180015b45  jmp     loc_180015BE3
0x180015b4a  lea     rbx, [rdi+40h]
0x180015b4e  mov     rcx, rbx; lpCriticalSection
0x180015b51  call    cs:__imp_EnterCriticalSection
0x180015b57  mov     [rsp+38h+arg_0], rbx
0x180015b5c  test    rsi, rsi
0x180015b5f  jnz     short loc_180015B8B
0x180015b61  mov     edi, 80070057h
0x180015b66  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180015b6d  jz      short loc_180015BCD
0x180015b6f  mov     [rsp+38h+var_18], 80070057h
0x180015b77  mov     r9d, 3D7h
0x180015b7d  lea     r8, aIpxMtfCmtfsugg_0; "ipx::mtf::CMtfSuggestionClient::AdviseL"...
0x180015b84  call    McTemplateU0sqq_EventWriteTransfer
0x180015b89  jmp     short loc_180015BCD
0x180015b8b  lea     r8, [rdi+80h]
0x180015b92  cmp     qword ptr [r8], 0
0x180015b96  jz      short loc_180015BB6
0x180015b98  mov     edi, 8000FFFFh
0x180015b9d  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180015ba4  jz      short loc_180015BCD
0x180015ba6  mov     [rsp+38h+var_18], 8000FFFFh
0x180015bae  mov     r9d, 3D9h
0x180015bb4  jmp     short loc_180015B7D
0x180015bb6  mov     rax, [rsi]
0x180015bb9  lea     rdx, IID_IMtfSuggestionLatticeNotify
0x180015bc0  mov     rcx, rsi
0x180015bc3  mov     rax, [rax]
0x180015bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bcb  mov     edi, eax
0x180015bcd  test    rbx, rbx
0x180015bd0  jz      short loc_180015BDB
0x180015bd2  mov     rcx, rbx; lpCriticalSection
0x180015bd5  call    cs:__imp_LeaveCriticalSection
0x180015bdb  mov     eax, edi
0x180015bdd  jmp     short loc_180015BE3
0x180015bdf  mov     eax, dword ptr [rsp+38h+arg_0]
0x180015be3  mov     rbx, [rsp+38h+arg_8]
0x180015be8  mov     rsi, [rsp+38h+arg_10]
0x180015bed  add     rsp, 30h
0x180015bf1  pop     rdi
0x180015bf2  retn
```
