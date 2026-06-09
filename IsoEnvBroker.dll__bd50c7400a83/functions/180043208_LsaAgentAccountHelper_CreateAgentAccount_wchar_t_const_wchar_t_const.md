# LsaAgentAccountHelper::CreateAgentAccount(wchar_t const *,wchar_t const *)

- ea: `0x180043208`
- end: `0x1800432fd`
- name: `?CreateAgentAccount@LsaAgentAccountHelper@@QEAAJPEB_W0@Z`
- size: `245`
- prototype: `int(LsaAgentAccountHelper *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180041b64`

## callees

- `0x1800075e4`
- `0x180043208`
- `0x180046af8`
- `0x180046bf4`
- `0x18006369c`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x18004322e`
- `ntdll!RtlInitUnicodeStringEx` at `0x18004324c`
- `ntdll!RtlInitUnicodeStringEx` at `0x18004322e`
- `ntdll!RtlInitUnicodeStringEx` at `0x18004324c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004328e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004328e`

## string_xrefs

- `0x1800432b7`: `onecoreuap\windows\core\isoenvbroker\lib\common\LsaAgentAccountHelper.h`
- `0x1800432d1`: `onecoreuap\windows\core\isoenvbroker\lib\common\LsaAgentAccountHelper.h`
- `0x1800432e8`: `onecoreuap\windows\core\isoenvbroker\lib\common\LsaAgentAccountHelper.h`

## pseudocode

```c
int __fastcall LsaAgentAccountHelper::CreateAgentAccount(
        LsaAgentAccountHelper *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const char *a4)
{
  NTSTATUS inited; // eax
  NTSTATUS v7; // eax
  int v8; // eax
  unsigned int v9; // r8d
  void *v11; // rcx
  char *v12; // rbx
  __int64 v13; // rax
  struct _UNICODE_STRING v14; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !*(_BYTE *)this )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x87,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\LsaAgentAccountHelper.h",
      a4);
  DestinationString = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, a2);
  if ( inited < 0 )
    wil::details::in1diag3::_FailFast_NtStatus(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\LsaAgentAccountHelper.h",
      (const char *)(unsigned int)inited,
      *(int *)&v14.Length);
  v14 = 0;
  v7 = RtlInitUnicodeStringEx(&v14, a3);
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_NtStatus(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\LsaAgentAccountHelper.h",
      (const char *)(unsigned int)v7,
      *(int *)&v14.Length);
  v8 = LsaCreateAgentAccount(*((_QWORD *)this + 1), &DestinationString, &v14);
  if ( v8 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x92,
             v9,
             (const char *)(unsigned int)v8,
             *(int *)&v14.Length);
  v11 = (void *)*((_QWORD *)this + 3);
  v12 = (char *)this + 16;
  if ( v11 )
  {
    LocalFree(v11);
    v13 = 16;
    do
    {
      *v12++ = 0;
      --v13;
    }
    while ( v13 );
  }
  return 0;
}

```

## disassembly

```asm
0x180043208  mov     [rsp+arg_0], rbx
0x18004320d  push    rdi
0x18004320e  sub     rsp, 40h
0x180043212  cmp     byte ptr [rcx], 0
0x180043215  mov     rdi, r8
0x180043218  mov     rbx, rcx
0x18004321b  jz      loc_1800432CC
0x180043221  xorps   xmm0, xmm0
0x180043224  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180043229  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18004322e  call    cs:__imp_RtlInitUnicodeStringEx
0x180043234  test    eax, eax
0x180043236  js      loc_1800432E3
0x18004323c  xorps   xmm0, xmm0
0x18004323f  lea     rcx, [rsp+48h+var_28]; DestinationString
0x180043244  mov     rdx, rdi; SourceString
0x180043247  movups  xmmword ptr [rsp+48h+var_28.Length], xmm0; int
0x18004324c  call    cs:__imp_RtlInitUnicodeStringEx
0x180043252  test    eax, eax
0x180043254  js      short loc_1800432B2
0x180043256  mov     rcx, [rbx+8]
0x18004325a  lea     r8, [rsp+48h+var_28]
0x18004325f  lea     rdx, [rsp+48h+DestinationString]
0x180043264  call    LsaCreateAgentAccount
0x180043269  test    eax, eax
0x18004326b  jns     short loc_180043281
0x18004326d  mov     rcx, [rsp+48h]; this
0x180043272  mov     r9d, eax; char *
0x180043275  mov     edx, 92h; void *
0x18004327a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004327f  jmp     short loc_1800432A7
0x180043281  mov     rcx, [rbx+18h]; hMem
0x180043285  add     rbx, 10h
0x180043289  test    rcx, rcx
0x18004328c  jz      short loc_1800432A5
0x18004328e  call    cs:__imp_LocalFree
0x180043294  mov     eax, 10h
0x180043299  mov     byte ptr [rbx], 0
0x18004329c  inc     rbx
0x18004329f  sub     rax, 1
0x1800432a3  jnz     short loc_180043299
0x1800432a5  xor     eax, eax
0x1800432a7  mov     rbx, [rsp+48h+arg_0]
0x1800432ac  add     rsp, 40h
0x1800432b0  pop     rdi
0x1800432b1  retn
0x1800432b2  mov     rcx, [rsp+48h]; this
0x1800432b7  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800432be  mov     r9d, eax; char *
0x1800432c1  mov     edx, 8Eh; void *
0x1800432c6  call    ?_FailFast_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_NtStatus(void *,uint,char const *,long)
0x1800432cc  mov     rcx, [rsp+48h]; this
0x1800432d1  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800432d8  mov     edx, 87h; void *
0x1800432dd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800432e3  mov     rcx, [rsp+48h]; this
0x1800432e8  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800432ef  mov     r9d, eax; char *
0x1800432f2  mov     edx, 8Ah; void *
0x1800432f7  call    ?_FailFast_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_NtStatus(void *,uint,char const *,long)
```
