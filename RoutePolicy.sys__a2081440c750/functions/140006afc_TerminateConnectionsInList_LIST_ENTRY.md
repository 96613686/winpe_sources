# TerminateConnectionsInList(_LIST_ENTRY *)

- ea: `0x140006afc`
- end: `0x140006cbe`
- name: `?TerminateConnectionsInList@@YAXPEAU_LIST_ENTRY@@@Z`
- size: `450`
- prototype: `void __fastcall(struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14000607c`
- `0x14000664c`

## callees

- `0x140001008`
- `0x1400012f0`
- `0x140004e54`
- `0x140005610`
- `0x140006afc`
- `0x14000a680`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006c3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006c3a`
- `NETIO!NsiSetAllParameters` at `0x140006b8e`
- `NETIO!NsiSetAllParameters` at `0x140006b8e`

## pseudocode

```c
void __fastcall TerminateConnectionsInList(struct _LIST_ENTRY *a1, __int64 a2, __int64 a3, __int64 a4)
{
  struct _LIST_ENTRY *Flink; // rdi
  __int16 v6; // ax
  int v7; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  struct _LIST_ENTRY *v10; // rcx
  struct _LIST_ENTRY *Blink; // rax
  int v12; // [rsp+40h] [rbp-78h] BYREF
  const char *v13; // [rsp+48h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+50h] [rbp-68h] BYREF
  int *v15; // [rsp+70h] [rbp-48h]
  __int64 v16; // [rsp+78h] [rbp-40h]

  while ( 1 )
  {
    Flink = a1->Flink;
    if ( a1->Flink == a1 )
      break;
    v6 = WORD2(Flink[2].Blink);
    if ( v6 != 2 && v6 != 23 )
    {
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v12 = WORD2(Flink[2].Blink);
        v16 = 4;
        v15 = &v12;
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, (unsigned __int8 *)&word_14000FD72, 0, 0, 3u, &v14);
      }
      return;
    }
    LOBYTE(a4) = 6;
    LogConnectionContextAddressPort(
      "TerminateConnectionsInList- Connection to terminate",
      &Flink[1],
      (char *)&Flink[2].Blink + 4,
      a4);
    v7 = NsiSetAllParameters(1, 2, NPI_MS_TCP_MODULEID);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v12 = v7;
        v13 = "NsiSetAllParameters failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)v7,
          (unsigned __int8 *)word_14000EBBA,
          v8,
          v9,
          (int **)&v13,
          (__int64)&v12);
      }
    }
    else if ( (unsigned int)dword_140012050 > 4 )
    {
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, (unsigned __int8 *)&dword_1400100AC, 0, 0, 2u, &v14);
    }
    FreeConnectionContext(Flink[4].Blink);
    v10 = Flink->Flink;
    if ( Flink->Flink->Blink != Flink || (Blink = Flink->Blink, Blink->Flink != Flink) )
      __fastfail(3u);
    Blink->Flink = v10;
    v10->Blink = Blink;
    ExFreePoolWithTag(Flink, 0x64667072u);
  }
}

```

## disassembly

```asm
0x140006afc  push    rbx
0x140006afe  push    rbp
0x140006aff  push    rsi
0x140006b00  push    rdi
0x140006b01  sub     rsp, 98h
0x140006b08  mov     rax, cs:__security_cookie
0x140006b0f  xor     rax, rsp
0x140006b12  mov     [rsp+0B8h+var_38], rax
0x140006b1a  mov     rsi, rcx
0x140006b1d  mov     ebp, 2
0x140006b22  mov     rdi, [rsi]
0x140006b25  cmp     rdi, rsi
0x140006b28  jz      loc_140006C9A
0x140006b2e  lea     rcx, [rdi+2Ch]
0x140006b32  movzx   eax, word ptr [rcx]
0x140006b35  cmp     ax, bp
0x140006b38  jz      short loc_140006B44
0x140006b3a  cmp     ax, 17h
0x140006b3e  jnz     loc_140006C4B
0x140006b44  mov     r8, rcx
0x140006b47  lea     rbx, [rdi+10h]
0x140006b4b  mov     rdx, rbx
0x140006b4e  lea     rcx, aTerminateconne; "TerminateConnectionsInList- Connection "...
0x140006b55  mov     r9b, 6
0x140006b58  call    LogConnectionContextAddressPort
0x140006b5d  mov     [rsp+0B8h+var_80], 0
0x140006b65  lea     r8, NPI_MS_TCP_MODULEID
0x140006b6c  mov     r9d, 10h
0x140006b72  mov     [rsp+0B8h+var_88], 0
0x140006b7b  mov     dword ptr [rsp+0B8h+var_90], 38h ; '8'
0x140006b83  mov     edx, ebp
0x140006b85  mov     qword ptr [rsp+0B8h+var_98], rbx
0x140006b8a  lea     ecx, [r9-0Fh]
0x140006b8e  call    cs:__imp_NsiSetAllParameters
0x140006b95  nop     dword ptr [rax+rax+00h]
0x140006b9a  mov     ecx, eax
0x140006b9c  test    eax, eax
0x140006b9e  mov     eax, cs:dword_140012050
0x140006ba4  js      short loc_140006BD4
0x140006ba6  cmp     eax, 4
0x140006ba9  jbe     short loc_140006C08
0x140006bab  lea     rax, [rsp+0B8h+var_68]
0x140006bb0  xor     r9d, r9d; int
0x140006bb3  mov     [rsp+0B8h+var_90], rax; PEVENT_DATA_DESCRIPTOR
0x140006bb8  lea     rdx, dword_1400100AC; int
0x140006bbf  xor     r8d, r8d; int
0x140006bc2  mov     [rsp+0B8h+var_98], ebp; ULONG
0x140006bc6  lea     rcx, dword_140012050; int
0x140006bcd  call    _tlgWriteTransfer_EtwWriteTransfer
0x140006bd2  jmp     short loc_140006C08
0x140006bd4  cmp     eax, ebp
0x140006bd6  jbe     short loc_140006C08
0x140006bd8  lea     rax, aNsisetallparam; "NsiSetAllParameters failed"
0x140006bdf  mov     [rsp+0B8h+var_78], ecx
0x140006be3  mov     [rsp+0B8h+var_70], rax
0x140006be8  lea     rdx, word_14000EBBA
0x140006bef  lea     rax, [rsp+0B8h+var_78]
0x140006bf4  mov     [rsp+0B8h+var_90], rax
0x140006bf9  lea     rax, [rsp+0B8h+var_70]
0x140006bfe  mov     qword ptr [rsp+0B8h+var_98], rax
0x140006c03  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140006c08  mov     rcx, [rdi+48h]; P
0x140006c0c  call    FreeConnectionContext
0x140006c11  mov     rcx, [rdi]
0x140006c14  cmp     [rcx+8], rdi
0x140006c18  jnz     loc_140006CB7
0x140006c1e  mov     rax, [rdi+8]
0x140006c22  cmp     [rax], rdi
0x140006c25  jnz     loc_140006CB7
0x140006c2b  mov     [rax], rcx
0x140006c2e  mov     edx, 64667072h; Tag
0x140006c33  mov     [rcx+8], rax
0x140006c37  mov     rcx, rdi; P
0x140006c3a  call    cs:__imp_ExFreePoolWithTag
0x140006c41  nop     dword ptr [rax+rax+00h]
0x140006c46  jmp     loc_140006B22
0x140006c4b  mov     eax, cs:dword_140012050
0x140006c51  cmp     eax, ebp
0x140006c53  jbe     short loc_140006C9A
0x140006c55  movzx   eax, word ptr [rcx]
0x140006c58  lea     rdx, word_14000FD72; int
0x140006c5f  mov     [rsp+0B8h+var_78], eax
0x140006c63  lea     rcx, dword_140012050; int
0x140006c6a  lea     rax, [rsp+0B8h+var_78]
0x140006c6f  mov     [rsp+0B8h+var_40], 4
0x140006c78  mov     [rsp+0B8h+var_48], rax
0x140006c7d  xor     r9d, r9d; int
0x140006c80  lea     rax, [rsp+0B8h+var_68]
0x140006c85  xor     r8d, r8d; int
0x140006c88  mov     [rsp+0B8h+var_90], rax; PEVENT_DATA_DESCRIPTOR
0x140006c8d  mov     [rsp+0B8h+var_98], 3; ULONG
0x140006c95  call    _tlgWriteTransfer_EtwWriteTransfer
0x140006c9a  mov     rcx, [rsp+0B8h+var_38]
0x140006ca2  xor     rcx, rsp; StackCookie
0x140006ca5  call    __security_check_cookie
0x140006caa  add     rsp, 98h
0x140006cb1  pop     rdi
0x140006cb2  pop     rsi
0x140006cb3  pop     rbp
0x140006cb4  pop     rbx
0x140006cb5  retn
0x140006cb7  mov     ecx, 3
0x140006cbc  int     29h; Win8: RtlFailFast(ecx)
```
