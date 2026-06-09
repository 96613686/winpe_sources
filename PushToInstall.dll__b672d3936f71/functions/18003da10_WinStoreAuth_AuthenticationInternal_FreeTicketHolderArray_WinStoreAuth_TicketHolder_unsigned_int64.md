# WinStoreAuth::AuthenticationInternal::FreeTicketHolderArray(WinStoreAuth::TicketHolder * *,unsigned __int64)

- ea: `0x18003da10`
- end: `0x18003da88`
- name: `?FreeTicketHolderArray@AuthenticationInternal@WinStoreAuth@@YAXPEAPEAUTicketHolder@2@_K@Z`
- size: `120`
- prototype: `void __fastcall(WinStoreAuth::AuthenticationInternal *__hidden this, struct WinStoreAuth::TicketHolder **, unsigned __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180035e4c`
- `0x180036174`
- `0x180039b08`
- `0x18003dcbc`
- `0x18003ef6c`

## callees

- `0x18003da10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003da3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003da56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003da3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003da56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003da70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003da70`

## pseudocode

```c
void __fastcall WinStoreAuth::AuthenticationInternal::FreeTicketHolderArray(
        LPVOID *this,
        struct WinStoreAuth::TicketHolder **a2)
{
  unsigned __int64 v4; // r14
  _QWORD *v5; // rbx
  __int64 v6; // rdi
  _QWORD *v7; // rbx

  if ( this && *this )
  {
    v4 = 0;
    if ( a2 )
    {
      do
      {
        v5 = *this;
        v6 = 3 * v4;
        WindowsDeleteString(*((HSTRING *)*this + 3 * v4 + 1));
        v5[3 * v4 + 1] = 0;
        v7 = *this;
        WindowsDeleteString(*((HSTRING *)*this + 3 * v4++ + 2));
        v7[v6 + 2] = 0;
      }
      while ( v4 < (unsigned __int64)a2 );
    }
    CoTaskMemFree(*this);
    *this = 0;
  }
}

```

## disassembly

```asm
0x18003da10  test    rcx, rcx
0x18003da13  jz      short locret_18003DA87
0x18003da15  push    rbx
0x18003da16  push    rbp
0x18003da17  push    rsi
0x18003da18  push    rdi
0x18003da19  push    r14
0x18003da1b  sub     rsp, 20h
0x18003da1f  cmp     qword ptr [rcx], 0
0x18003da23  mov     rbp, rdx
0x18003da26  mov     rsi, rcx
0x18003da29  jz      short loc_18003DA7D
0x18003da2b  xor     r14d, r14d
0x18003da2e  test    rdx, rdx
0x18003da31  jz      short loc_18003DA6D
0x18003da33  mov     rbx, [rsi]
0x18003da36  lea     rdi, [r14+r14*2]
0x18003da3a  mov     rcx, [rbx+rdi*8+8]; string
0x18003da3f  call    cs:__imp_WindowsDeleteString
0x18003da45  mov     qword ptr [rbx+rdi*8+8], 0
0x18003da4e  mov     rbx, [rsi]
0x18003da51  mov     rcx, [rbx+rdi*8+10h]; string
0x18003da56  call    cs:__imp_WindowsDeleteString
0x18003da5c  inc     r14
0x18003da5f  mov     qword ptr [rbx+rdi*8+10h], 0
0x18003da68  cmp     r14, rbp
0x18003da6b  jb      short loc_18003DA33
0x18003da6d  mov     rcx, [rsi]; pv
0x18003da70  call    cs:__imp_CoTaskMemFree
0x18003da76  mov     qword ptr [rsi], 0
0x18003da7d  add     rsp, 20h
0x18003da81  pop     r14
0x18003da83  pop     rdi
0x18003da84  pop     rsi
0x18003da85  pop     rbp
0x18003da86  pop     rbx
0x18003da87  retn
```
