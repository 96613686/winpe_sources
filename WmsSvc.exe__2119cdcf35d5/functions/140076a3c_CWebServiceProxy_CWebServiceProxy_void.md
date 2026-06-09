# CWebServiceProxy::~CWebServiceProxy(void)

- ea: `0x140076a3c`
- end: `0x140076ad8`
- name: `??1CWebServiceProxy@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(CWebServiceProxy *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140055b34`
- `0x14005633c`
- `0x140076ae0`

## callees

- `0x140076a3c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140076abe`
- `OLEAUT32!__imp_SysFreeString` at `0x140076acb`
- `OLEAUT32!__imp_SysFreeString` at `0x140076abe`
- `OLEAUT32!__imp_SysFreeString` at `0x140076acb`
- `webservices!WsCloseServiceProxy` at `0x140076a66`
- `webservices!WsCloseServiceProxy` at `0x140076a66`
- `webservices!WsFreeServiceProxy` at `0x140076a73`
- `webservices!WsFreeServiceProxy` at `0x140076a73`
- `webservices!WsFreeHeap` at `0x140076aa2`
- `webservices!WsFreeHeap` at `0x140076aa2`
- `webservices!WsFreeError` at `0x140076ab1`
- `webservices!WsFreeError` at `0x140076ab1`

## pseudocode

```c
void __fastcall CWebServiceProxy::~CWebServiceProxy(CWebServiceProxy *this)
{
  WS_SERVICE_PROXY *v2; // rcx
  _DWORD *v3; // rax
  __int64 v4; // rcx
  _BYTE *v5; // rax
  WS_HEAP *v6; // rcx
  WS_ERROR *v7; // rcx

  *(_QWORD *)this = &CWebServiceProxy::`vftable';
  v2 = (WS_SERVICE_PROXY *)*((_QWORD *)this + 39);
  if ( v2 )
  {
    if ( *((_DWORD *)this + 6) )
      WsCloseServiceProxy(v2, 0, 0);
    WsFreeServiceProxy(*((WS_SERVICE_PROXY **)this + 39));
  }
  v3 = (_DWORD *)((char *)this + 56);
  if ( this != (CWebServiceProxy *)-56LL && *v3 )
  {
    v4 = (unsigned int)*v3;
    v5 = (_BYTE *)*((_QWORD *)this + 8);
    do
    {
      *v5++ = 0;
      --v4;
    }
    while ( v4 );
  }
  v6 = (WS_HEAP *)*((_QWORD *)this + 2);
  if ( v6 )
    WsFreeHeap(v6);
  v7 = (WS_ERROR *)*((_QWORD *)this + 1);
  if ( v7 )
    WsFreeError(v7);
  SysFreeString(*((BSTR *)this + 40));
  SysFreeString(*((BSTR *)this + 41));
}

```

## disassembly

```asm
0x140076a3c  push    rbx
0x140076a3e  sub     rsp, 20h
0x140076a42  mov     rbx, rcx
0x140076a45  lea     rax, ??_7CWebServiceProxy@@6B@; const CWebServiceProxy::`vftable'
0x140076a4c  mov     [rcx], rax
0x140076a4f  mov     rcx, [rcx+138h]; serviceProxy
0x140076a56  test    rcx, rcx
0x140076a59  jz      short loc_140076A79
0x140076a5b  cmp     dword ptr [rbx+18h], 0
0x140076a5f  jz      short loc_140076A6C
0x140076a61  xor     r8d, r8d; error
0x140076a64  xor     edx, edx; asyncContext
0x140076a66  call    cs:__imp_WsCloseServiceProxy
0x140076a6c  mov     rcx, [rbx+138h]; serviceProxy
0x140076a73  call    cs:__imp_WsFreeServiceProxy
0x140076a79  lea     rax, [rbx+38h]
0x140076a7d  test    rax, rax
0x140076a80  jz      short loc_140076A99
0x140076a82  cmp     dword ptr [rax], 0
0x140076a85  jz      short loc_140076A99
0x140076a87  mov     ecx, [rax]
0x140076a89  mov     rax, [rbx+40h]
0x140076a8d  mov     byte ptr [rax], 0
0x140076a90  inc     rax
0x140076a93  sub     rcx, 1
0x140076a97  jnz     short loc_140076A8D
0x140076a99  mov     rcx, [rbx+10h]; heap
0x140076a9d  test    rcx, rcx
0x140076aa0  jz      short loc_140076AA8
0x140076aa2  call    cs:__imp_WsFreeHeap
0x140076aa8  mov     rcx, [rbx+8]; error
0x140076aac  test    rcx, rcx
0x140076aaf  jz      short loc_140076AB7
0x140076ab1  call    cs:__imp_WsFreeError
0x140076ab7  mov     rcx, [rbx+140h]; bstrString
0x140076abe  call    cs:__imp_SysFreeString
0x140076ac4  mov     rcx, [rbx+148h]; bstrString
0x140076acb  call    cs:__imp_SysFreeString
0x140076ad1  nop
0x140076ad2  add     rsp, 20h
0x140076ad6  pop     rbx
0x140076ad7  retn
```
