# _lambda_19a98c5a81a3f7f216e793bf8327e4a2_::_lambda_invoker_cdecl_(HSWDEVICE__ *,long,void *,ushort const *)

- ea: `0x18000bbf0`
- end: `0x18000bc26`
- name: `?_lambda_invoker_cdecl_@_lambda_19a98c5a81a3f7f216e793bf8327e4a2_@@CAXPEAUHSWDEVICE__@@JPEAXPEBG@Z`
- size: `54`
- prototype: `void __fastcall(struct HSWDEVICE__ *, int, _QWORD *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009260`
- `0x18000bbf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000bc00`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000bc00`

## string_xrefs

- `0x18000bc14`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall _lambda_19a98c5a81a3f7f216e793bf8327e4a2_::_lambda_invoker_cdecl_(
        struct HSWDEVICE__ *a1,
        int a2,
        _QWORD *a3,
        const unsigned __int16 *a4)
{
  void *v4; // rcx
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a3 )
  {
    v4 = (void *)a3[1];
    *(_DWORD *)a3 = a2;
    if ( !SetEvent(v4) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA01,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v5);
  }
}

```

## disassembly

```asm
0x18000bbf0  sub     rsp, 28h
0x18000bbf4  test    r8, r8
0x18000bbf7  jz      short loc_18000BC0A
0x18000bbf9  mov     rcx, [r8+8]; hEvent
0x18000bbfd  mov     [r8], edx
0x18000bc00  call    cs:__imp_SetEvent
0x18000bc06  test    eax, eax
0x18000bc08  jz      short loc_18000BC0F
0x18000bc0a  add     rsp, 28h
0x18000bc0e  retn
0x18000bc0f  mov     rcx, [rsp+28h]; this
0x18000bc14  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bc1b  mov     edx, 0A01h; void *
0x18000bc20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
