# CMsmqVssWriter::RestoreServiceRegistry(wchar_t const *)

- ea: `0x180093cdc`
- end: `0x180093e36`
- name: `?RestoreServiceRegistry@CMsmqVssWriter@@AEAAJPEB_W@Z`
- size: `346`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009331c`

## callees

- `0x18000f35c`
- `0x180012ea8`
- `0x18002c61c`
- `0x1800929fc`
- `0x180093cdc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180093d26`
- `KERNEL32!GetLastError` at `0x180093db8`
- `KERNEL32!GetLastError` at `0x180093d26`
- `KERNEL32!GetLastError` at `0x180093db8`
- `ktmw32!CreateTransaction` at `0x180093d12`
- `ktmw32!CreateTransaction` at `0x180093d12`
- `ktmw32!CommitTransaction` at `0x180093dae`
- `ktmw32!CommitTransaction` at `0x180093dae`

## string_xrefs

- `0x180093d99`: `writer/mqwriter`
- `0x180093e08`: `writer/mqwriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMsmqVssWriter::RestoreServiceRegistry(CMsmqVssWriter *this, const wchar_t *a2)
{
  HANDLE Transaction; // rax
  void *v5; // rbx
  signed int LastError; // eax
  signed int v7; // ebx
  unsigned __int16 v8; // r8
  int v9; // eax
  signed int v10; // edi
  signed int v11; // eax
  HANDLE v13; // [rsp+60h] [rbp+18h] BYREF

  Transaction = CreateTransaction(0, 0, 0, 0, 0, 0, 0);
  v5 = Transaction;
  v13 = Transaction;
  if ( Transaction == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_6af5f41940d83573eba81ec716aa4ffa_Traceguids,
        (unsigned int)v7);
    if ( v7 < 0 )
    {
      v8 = 104;
LABEL_19:
      LogMsgHR(v7, (wchar_t *)L"writer/mqwriter", v8);
    }
  }
  else
  {
    v9 = CMsmqVssWriter::RestoreRegistry(this, a2, Transaction);
    v10 = v9;
    if ( v9 >= 0 )
    {
      if ( CommitTransaction(v5) )
      {
        v7 = 0;
        goto LABEL_21;
      }
      v11 = GetLastError();
      v7 = v11;
      if ( v11 > 0 )
        v7 = (unsigned __int16)v11 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_6af5f41940d83573eba81ec716aa4ffa_Traceguids,
          (unsigned int)v7);
      if ( v7 < 0 )
      {
        v8 = 140;
        goto LABEL_19;
      }
    }
    else
    {
      LogMsgHR(v9, (wchar_t *)L"writer/mqwriter", 0x78u);
      v7 = v10;
    }
  }
LABEL_21:
  CHandle::~CHandle((CHandle *)&v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180093cdc  mov     rax, rsp
0x180093cdf  mov     [rax+8], rbx
0x180093ce3  mov     [rax+10h], rsi
0x180093ce7  push    rdi
0x180093ce8  sub     rsp, 40h
0x180093cec  mov     rdi, rdx
0x180093cef  mov     rsi, rcx
0x180093cf2  mov     qword ptr [rax-18h], 0
0x180093cfa  mov     dword ptr [rax-20h], 0
0x180093d01  mov     dword ptr [rax-28h], 0
0x180093d08  xor     r9d, r9d; IsolationLevel
0x180093d0b  xor     r8d, r8d; CreateOptions
0x180093d0e  xor     edx, edx; UOW
0x180093d10  xor     ecx, ecx; lpTransactionAttributes
0x180093d12  call    cs:__imp_CreateTransaction
0x180093d18  mov     rbx, rax
0x180093d1b  mov     [rsp+48h+arg_10], rax
0x180093d20  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180093d24  jnz     short loc_180093D7F
0x180093d26  call    cs:__imp_GetLastError
0x180093d2c  mov     ebx, eax
0x180093d2e  test    eax, eax
0x180093d30  jle     short loc_180093D3B
0x180093d32  movzx   ebx, ax
0x180093d35  or      ebx, 80070000h
0x180093d3b  lea     rax, WPP_GLOBAL_Control
0x180093d42  mov     rcx, cs:WPP_GLOBAL_Control
0x180093d49  cmp     rcx, rax
0x180093d4c  jz      short loc_180093D6C
0x180093d4e  test    byte ptr [rcx+1Ch], 1
0x180093d52  jz      short loc_180093D6C
0x180093d54  mov     edx, 0Ch
0x180093d59  mov     r9d, ebx
0x180093d5c  lea     r8, WPP_6af5f41940d83573eba81ec716aa4ffa_Traceguids
0x180093d63  mov     rcx, [rcx+10h]
0x180093d67  call    WPP_SF_d
0x180093d6c  test    ebx, ebx
0x180093d6e  jns     loc_180093E1A
0x180093d74  mov     r8d, 68h ; 'h'
0x180093d7a  jmp     loc_180093E08
0x180093d7f  mov     r8, rbx; void *
0x180093d82  mov     rdx, rdi; wchar_t *
0x180093d85  mov     rcx, rsi; this
0x180093d88  call    ?RestoreRegistry@CMsmqVssWriter@@AEAAJPEB_WPEAX@Z; CMsmqVssWriter::RestoreRegistry(wchar_t const *,void *)
0x180093d8d  mov     edi, eax
0x180093d8f  test    eax, eax
0x180093d91  jns     short loc_180093DAB
0x180093d93  mov     r8d, 78h ; 'x'; unsigned __int16
0x180093d99  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180093da0  mov     ecx, eax; int
0x180093da2  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180093da7  mov     ebx, edi
0x180093da9  jmp     short loc_180093E1A
0x180093dab  mov     rcx, rbx; TransactionHandle
0x180093dae  call    cs:__imp_CommitTransaction
0x180093db4  test    eax, eax
0x180093db6  jnz     short loc_180093E18
0x180093db8  call    cs:__imp_GetLastError
0x180093dbe  mov     ebx, eax
0x180093dc0  test    eax, eax
0x180093dc2  jle     short loc_180093DCD
0x180093dc4  movzx   ebx, ax
0x180093dc7  or      ebx, 80070000h
0x180093dcd  lea     rax, WPP_GLOBAL_Control
0x180093dd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180093ddb  cmp     rcx, rax
0x180093dde  jz      short loc_180093DFE
0x180093de0  test    byte ptr [rcx+1Ch], 1
0x180093de4  jz      short loc_180093DFE
0x180093de6  mov     edx, 0Dh
0x180093deb  mov     r9d, ebx
0x180093dee  lea     r8, WPP_6af5f41940d83573eba81ec716aa4ffa_Traceguids
0x180093df5  mov     rcx, [rcx+10h]
0x180093df9  call    WPP_SF_d
0x180093dfe  test    ebx, ebx
0x180093e00  jns     short loc_180093E1A
0x180093e02  mov     r8d, 8Ch; unsigned __int16
0x180093e08  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180093e0f  mov     ecx, ebx; int
0x180093e11  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180093e16  jmp     short loc_180093E1A
0x180093e18  xor     ebx, ebx
0x180093e1a  lea     rcx, [rsp+48h+arg_10]; this
0x180093e1f  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180093e24  mov     eax, ebx
0x180093e26  mov     rbx, [rsp+48h+arg_0]
0x180093e2b  mov     rsi, [rsp+48h+arg_8]
0x180093e30  add     rsp, 40h
0x180093e34  pop     rdi
0x180093e35  retn
```
