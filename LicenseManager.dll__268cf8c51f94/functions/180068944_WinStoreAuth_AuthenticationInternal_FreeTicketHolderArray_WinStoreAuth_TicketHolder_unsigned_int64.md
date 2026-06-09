# WinStoreAuth::AuthenticationInternal::FreeTicketHolderArray(WinStoreAuth::TicketHolder * *,unsigned __int64)

- ea: `0x180068944`
- end: `0x1800689bc`
- name: `?FreeTicketHolderArray@AuthenticationInternal@WinStoreAuth@@YAXPEAPEAUTicketHolder@2@_K@Z`
- size: `120`
- prototype: `void __fastcall(WinStoreAuth::AuthenticationInternal *__hidden this, struct WinStoreAuth::TicketHolder **, unsigned __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003bf58`
- `0x18006891c`
- `0x18006a520`

## callees

- `0x180068944`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068973`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006898a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068973`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006898a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800689a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800689a4`

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
0x180068944  test    rcx, rcx
0x180068947  jz      short locret_1800689BB
0x180068949  push    rbx
0x18006894a  push    rbp
0x18006894b  push    rsi
0x18006894c  push    rdi
0x18006894d  push    r14
0x18006894f  sub     rsp, 20h
0x180068953  cmp     qword ptr [rcx], 0
0x180068957  mov     rbp, rdx
0x18006895a  mov     rsi, rcx
0x18006895d  jz      short loc_1800689B1
0x18006895f  xor     r14d, r14d
0x180068962  test    rdx, rdx
0x180068965  jz      short loc_1800689A1
0x180068967  mov     rbx, [rsi]
0x18006896a  lea     rdi, [r14+r14*2]
0x18006896e  mov     rcx, [rbx+rdi*8+8]; string
0x180068973  call    cs:__imp_WindowsDeleteString
0x180068979  mov     qword ptr [rbx+rdi*8+8], 0
0x180068982  mov     rbx, [rsi]
0x180068985  mov     rcx, [rbx+rdi*8+10h]; string
0x18006898a  call    cs:__imp_WindowsDeleteString
0x180068990  inc     r14
0x180068993  mov     qword ptr [rbx+rdi*8+10h], 0
0x18006899c  cmp     r14, rbp
0x18006899f  jb      short loc_180068967
0x1800689a1  mov     rcx, [rsi]; pv
0x1800689a4  call    cs:__imp_CoTaskMemFree
0x1800689aa  mov     qword ptr [rsi], 0
0x1800689b1  add     rsp, 20h
0x1800689b5  pop     r14
0x1800689b7  pop     rdi
0x1800689b8  pop     rsi
0x1800689b9  pop     rbp
0x1800689ba  pop     rbx
0x1800689bb  retn
```
