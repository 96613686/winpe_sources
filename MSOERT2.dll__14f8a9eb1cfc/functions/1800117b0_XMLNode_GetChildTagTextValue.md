# XMLNode_GetChildTagTextValue

- ea: `0x1800117b0`
- end: `0x180011819`
- name: `XMLNode_GetChildTagTextValue`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180001c50`
- `0x1800116c0`
- `0x1800117b0`
- `0x180011820`

## pseudocode

```c
__int64 __fastcall XMLNode_GetChildTagTextValue(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        BSTR *a3)
{
  int ChildTag; // ebx
  __int64 *v6; // [rsp+30h] [rbp+8h] BYREF

  if ( !a1 || !a2 || !a3 )
    return 2147942487LL;
  *a3 = 0;
  v6 = 0;
  ChildTag = XMLNode_GetChildTag(a1, a2, &v6);
  if ( ChildTag >= 0 )
  {
    ChildTag = XMLNode_GetTagText(v6, a3);
    OE_SafeReleaseAndNullPtr<CFileStream>(&v6);
  }
  return (unsigned int)ChildTag;
}

```

## disassembly

```asm
0x1800117b0  mov     [rsp+arg_8], rbx
0x1800117b5  push    rdi
0x1800117b6  sub     rsp, 20h
0x1800117ba  mov     rdi, r8
0x1800117bd  test    rcx, rcx
0x1800117c0  jz      short loc_180011809
0x1800117c2  test    rdx, rdx
0x1800117c5  jz      short loc_180011809
0x1800117c7  test    r8, r8
0x1800117ca  jz      short loc_180011809
0x1800117cc  mov     qword ptr [r8], 0
0x1800117d3  lea     r8, [rsp+28h+arg_0]
0x1800117d8  mov     [rsp+28h+arg_0], 0
0x1800117e1  call    XMLNode_GetChildTag
0x1800117e6  mov     ebx, eax
0x1800117e8  test    eax, eax
0x1800117ea  js      short loc_180011805
0x1800117ec  mov     rcx, [rsp+28h+arg_0]
0x1800117f1  mov     rdx, rdi
0x1800117f4  call    XMLNode_GetTagText
0x1800117f9  lea     rcx, [rsp+28h+arg_0]
0x1800117fe  mov     ebx, eax
0x180011800  call    ??$OE_SafeReleaseAndNullPtr@VCFileStream@@@@YAXAEAPEAVCFileStream@@@Z; OE_SafeReleaseAndNullPtr<CFileStream>(CFileStream * &)
0x180011805  mov     eax, ebx
0x180011807  jmp     short loc_18001180E
0x180011809  mov     eax, 80070057h
0x18001180e  mov     rbx, [rsp+28h+arg_8]
0x180011813  add     rsp, 20h
0x180011817  pop     rdi
0x180011818  retn
```
