# FreeTempFileList

- ea: `0x18000b340`
- end: `0x18000b383`
- name: `FreeTempFileList`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001280`

## callees

- `0x180009268`
- `0x18000b340`

## pseudocode

```c
_QWORD *__fastcall FreeTempFileList(struct TEMPFILELIST *a1)
{
  int v1; // ebx
  _QWORD *result; // rax
  struct TEMPFILELIST *v3; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    v3 = a1;
    v1 = 0;
    if ( a1 == g_pTempFileHead )
    {
      v1 = 1;
      dword_1800209F8 = 1;
    }
    result = OE_SafeReleaseAndNullPtr<TEMPFILELIST>(&v3);
    if ( v1 )
      dword_1800209F8 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000b340  test    rcx, rcx
0x18000b343  jz      short locret_18000B382
0x18000b345  mov     [rsp+arg_0], rcx
0x18000b34a  push    rbx
0x18000b34b  sub     rsp, 20h
0x18000b34f  xor     ebx, ebx
0x18000b351  cmp     rcx, cs:?g_pTempFileHead@@3PEAVTEMPFILELIST@@EA; TEMPFILELIST * g_pTempFileHead
0x18000b358  jnz     short loc_18000B365
0x18000b35a  mov     ebx, 1
0x18000b35f  mov     cs:dword_1800209F8, ebx
0x18000b365  lea     rcx, [rsp+28h+arg_0]
0x18000b36a  call    ??$OE_SafeReleaseAndNullPtr@VTEMPFILELIST@@@@YAXAEAPEAVTEMPFILELIST@@@Z; OE_SafeReleaseAndNullPtr<TEMPFILELIST>(TEMPFILELIST * &)
0x18000b36f  test    ebx, ebx
0x18000b371  jz      short loc_18000B37D
0x18000b373  mov     cs:dword_1800209F8, 0
0x18000b37d  add     rsp, 20h
0x18000b381  pop     rbx
0x18000b382  retn
```
