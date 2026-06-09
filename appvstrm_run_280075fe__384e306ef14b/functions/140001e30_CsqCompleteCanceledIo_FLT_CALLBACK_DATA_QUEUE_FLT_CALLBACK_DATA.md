# CsqCompleteCanceledIo(_FLT_CALLBACK_DATA_QUEUE *,_FLT_CALLBACK_DATA *)

- ea: `0x140001e30`
- end: `0x140001efa`
- name: `?CsqCompleteCanceledIo@@YAXPEAU_FLT_CALLBACK_DATA_QUEUE@@PEAU_FLT_CALLBACK_DATA@@@Z`
- size: `202`
- prototype: `void __stdcall(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140001e30`
- `0x1400147fc`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `FLTMGR!FltCompletePendedPreOperation` at `0x140001edd`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140001edd`

## string_xrefs

- `0x140001e79`: `CsqCompleteCanceledIo() - Stream fault was canceled. File name: %s, Offset: %lld, Length %ld, Status 0x%08X.`

## pseudocode

```c
void __fastcall CsqCompleteCanceledIo(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  ULONG Length; // ebx
  LARGE_INTEGER ByteOffset; // rdi
  __int64 *CurrentActivityID; // rax
  volatile signed __int32 *v7; // rbx
  ULONG v8; // [rsp+28h] [rbp-30h]
  int v9; // [rsp+30h] [rbp-28h]
  char v10[8]; // [rsp+40h] [rbp-18h] BYREF
  volatile signed __int32 *v11; // [rsp+48h] [rbp-10h]

  Iopb = Cbd->Iopb;
  Cbd->IoStatus.Status = -1073741536;
  Cbd->IoStatus.Information = 0;
  Length = Iopb->Parameters.Read.Length;
  ByteOffset = Iopb->Parameters.Read.ByteOffset;
  CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(v10);
  v9 = -1073741536;
  v8 = Length;
  LogWrite(
    2,
    *CurrentActivityID,
    L"CsqCompleteCanceledIo() - Stream fault was canceled. File name: %s, Offset: %lld, Length %ld, Status 0x%08X.",
    &SourceString,
    ByteOffset.QuadPart,
    v8,
    v9);
  v7 = v11;
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  FltCompletePendedPreOperation(Cbd, FLT_PREOP_COMPLETE, 0);
}

```

## disassembly

```asm
0x140001e30  mov     [rsp+arg_0], rbx
0x140001e35  mov     [rsp+arg_8], rsi
0x140001e3a  push    rdi
0x140001e3b  sub     rsp, 50h
0x140001e3f  mov     rax, [rdx+10h]
0x140001e43  lea     rcx, [rsp+58h+var_18]
0x140001e48  mov     dword ptr [rdx+18h], 0C0000120h
0x140001e4f  mov     rsi, rdx
0x140001e52  mov     qword ptr [rdx+20h], 0
0x140001e5a  mov     ebx, [rax+18h]
0x140001e5d  mov     rdi, [rax+28h]
0x140001e61  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140001e66  mov     [rsp+58h+var_28], 0C0000120h
0x140001e6e  lea     r9, SourceString
0x140001e75  mov     [rsp+58h+var_30], ebx
0x140001e79  lea     r8, aCsqcompletecan; "CsqCompleteCanceledIo() - Stream fault "...
0x140001e80  mov     ecx, 2
0x140001e85  mov     [rsp+58h+var_38], rdi
0x140001e8a  mov     rdx, [rax]
0x140001e8d  call    LogWrite
0x140001e92  mov     rbx, [rsp+58h+var_10]
0x140001e97  test    rbx, rbx
0x140001e9a  jz      short loc_140001ED3
0x140001e9c  or      edi, 0FFFFFFFFh
0x140001e9f  mov     eax, edi
0x140001ea1  lock xadd [rbx+8], eax
0x140001ea6  add     eax, edi
0x140001ea8  jnz     short loc_140001ED3
0x140001eaa  mov     rax, [rbx]
0x140001ead  mov     rcx, rbx
0x140001eb0  mov     rax, [rax+8]
0x140001eb4  call    _guard_dispatch_icall
0x140001eb9  mov     eax, edi
0x140001ebb  lock xadd [rbx+0Ch], eax
0x140001ec0  add     eax, edi
0x140001ec2  jnz     short loc_140001ED3
0x140001ec4  mov     rax, [rbx]
0x140001ec7  mov     rcx, rbx
0x140001eca  mov     rax, [rax+10h]
0x140001ece  call    _guard_dispatch_icall
0x140001ed3  xor     r8d, r8d; Context
0x140001ed6  mov     rcx, rsi; CallbackData
0x140001ed9  lea     edx, [r8+4]; CallbackStatus
0x140001edd  call    cs:__imp_FltCompletePendedPreOperation
0x140001ee4  nop     dword ptr [rax+rax+00h]
0x140001ee9  mov     rbx, [rsp+58h+arg_0]
0x140001eee  mov     rsi, [rsp+58h+arg_8]
0x140001ef3  add     rsp, 50h
0x140001ef7  pop     rdi
0x140001ef8  retn
```
