# wil::details::CloseHandle(void *)

- ea: `0x40ae71`
- end: `0x40ae97`
- name: `?CloseHandle@details@wil@@YGXPAX@Z`
- size: `38`
- prototype: `void __stdcall(HANDLE hObject, void *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x40b08b`
- `0x40c066`
- `0x40c3ba`
- `0x40c5cc`
- `0x40c5f7`

## callees

- `0x40ae34`
- `0x40ae71`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x40ae7a`
- `KERNEL32!CloseHandle` at `0x40ae7a`

## pseudocode

```c

```

## disassembly

```asm
0x40ae71  mov     edi, edi
0x40ae73  push    ebp; unsigned int
0x40ae74  mov     ebp, esp
0x40ae76  push    ecx; void *
0x40ae77  push    [ebp+hObject]; hObject
0x40ae7a  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x40ae80  test    eax, eax
0x40ae82  jz      short loc_40AE89
0x40ae84  pop     ecx
0x40ae85  pop     ebp
0x40ae86  retn    4
0x40ae89  push    ecx; this
0x40ae8a  mov     ecx, [ebp+4]
0x40ae8d  mov     edx, 0A0Bh
0x40ae92  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YGXPAXIPBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
