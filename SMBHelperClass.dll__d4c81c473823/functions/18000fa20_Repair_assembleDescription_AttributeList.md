# Repair::assembleDescription(AttributeList *)

- ea: `0x18000fa20`
- end: `0x18000fa90`
- name: `?assembleDescription@Repair@@UEAAPEAGPEAVAttributeList@@@Z`
- size: `112`
- prototype: `unsigned __int16 *(Repair *__hidden this, struct AttributeList *)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000a000`
- `0x18000a900`
- `0x18000b290`
- `0x18000b2e0`
- `0x18000b330`
- `0x18000b380`

## callees

- `0x18000e594`
- `0x18000e6a8`
- `0x18000fa20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fa77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fa77`

## pseudocode

```c
unsigned __int16 *__fastcall Repair::assembleDescription(Repair *this, struct AttributeList *a2)
{
  unsigned __int16 *v4; // rbx
  unsigned __int16 *v5; // rsi
  unsigned __int16 *result; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h] BYREF
  unsigned __int16 *v10; // [rsp+50h] [rbp+18h] BYREF

  v4 = (unsigned __int16 *)*((_QWORD *)this + 4);
  v10 = v4;
  if ( (unsigned __int64)v4 < 0x10000 )
  {
    AllocateAndLoadString(&v10, v4);
    v4 = v10;
  }
  try
  {
    v5 = AssembleDescription(v4, a2);
    if ( *((_QWORD *)this + 4) < 0x10000u )
      CoTaskMemFree(v4);
    result = v5;
  }
  catch ( TestException v8 )
  {
    if ( (*((_QWORD *)this + 4) & 0xFFFFFFFFFFFF0000uLL) == 0 )
      FreeTestMemory(v10);
    v7 = v8;
    throw (TestException *)&v7;
  }
  return result;
}

```

## disassembly

```asm
0x18000fa20  mov     rax, rsp
0x18000fa23  mov     [rax+10h], rbx
0x18000fa27  mov     [rax+20h], rsi
0x18000fa2b  mov     [rax+8], rcx
0x18000fa2f  push    rdi
0x18000fa30  sub     rsp, 30h
0x18000fa34  mov     rsi, rdx
0x18000fa37  mov     rdi, rcx
0x18000fa3a  mov     rbx, [rcx+20h]
0x18000fa3e  mov     [rax+18h], rbx
0x18000fa42  cmp     rbx, 10000h
0x18000fa49  jnb     short loc_18000FA5C
0x18000fa4b  mov     rdx, rbx; unsigned __int16 *
0x18000fa4e  lea     rcx, [rax+18h]; unsigned __int16 **
0x18000fa52  call    ?AllocateAndLoadString@@YAXPEAPEAGPEAG@Z; AllocateAndLoadString(ushort * *,ushort *)
0x18000fa57  mov     rbx, [rsp+38h+arg_10]
0x18000fa5c  mov     rdx, rsi; struct AttributeList *
0x18000fa5f  mov     rcx, rbx; unsigned __int16 *
0x18000fa62  call    ?AssembleDescription@@YAPEAGPEAGPEAVAttributeList@@@Z; AssembleDescription(ushort *,AttributeList *)
0x18000fa67  mov     rsi, rax
0x18000fa6a  cmp     qword ptr [rdi+20h], 10000h
0x18000fa72  jnb     short loc_18000FA7D
0x18000fa74  mov     rcx, rbx; pv
0x18000fa77  call    cs:__imp_CoTaskMemFree
0x18000fa7d  mov     rax, rsi
0x18000fa80  mov     rbx, [rsp+38h+arg_8]
0x18000fa85  mov     rsi, [rsp+38h+arg_18]
0x18000fa8a  add     rsp, 30h
0x18000fa8e  pop     rdi
0x18000fa8f  retn
```
