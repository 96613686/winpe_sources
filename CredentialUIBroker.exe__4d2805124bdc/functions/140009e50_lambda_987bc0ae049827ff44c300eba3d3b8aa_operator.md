# _lambda_987bc0ae049827ff44c300eba3d3b8aa_::operator()

- ea: `0x140009e50`
- end: `0x140009ebb`
- name: `_lambda_987bc0ae049827ff44c300eba3d3b8aa_::operator()`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140008b98`

## callees

- `0x140009e50`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140009eb4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140009e76`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140009e76`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140009ea2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140009ea2`

## pseudocode

```c
HRESULT __fastcall lambda_987bc0ae049827ff44c300eba3d3b8aa_::operator()(unsigned int **a1)
{
  SAFEARRAY **v2; // rcx
  __int64 v3; // rcx
  _BYTE *v4; // rax
  void *ppvData; // [rsp+30h] [rbp+8h] BYREF

  if ( **a1 )
  {
    v2 = (SAFEARRAY **)a1[1];
    ppvData = 0;
    if ( SafeArrayAccessData(*v2, &ppvData) >= 0 )
    {
      v3 = **a1;
      v4 = ppvData;
      if ( **a1 )
      {
        do
        {
          *v4++ = 0;
          --v3;
        }
        while ( v3 );
      }
      SafeArrayUnaccessData(*(SAFEARRAY **)a1[1]);
    }
  }
  return SafeArrayDestroy(*(SAFEARRAY **)a1[1]);
}

```

## disassembly

```asm
0x140009e50  push    rbx
0x140009e52  sub     rsp, 20h
0x140009e56  mov     rax, [rcx]
0x140009e59  mov     rbx, rcx
0x140009e5c  cmp     dword ptr [rax], 0
0x140009e5f  jbe     short loc_140009EA8
0x140009e61  mov     rcx, [rcx+8]
0x140009e65  lea     rdx, [rsp+28h+ppvData]; ppvData
0x140009e6a  mov     [rsp+28h+ppvData], 0
0x140009e73  mov     rcx, [rcx]; psa
0x140009e76  call    cs:__imp_SafeArrayAccessData
0x140009e7c  test    eax, eax
0x140009e7e  js      short loc_140009EA8
0x140009e80  mov     rax, [rbx]
0x140009e83  mov     ecx, [rax]
0x140009e85  mov     rax, [rsp+28h+ppvData]
0x140009e8a  test    rcx, rcx
0x140009e8d  jz      short loc_140009E9B
0x140009e8f  mov     byte ptr [rax], 0
0x140009e92  inc     rax
0x140009e95  sub     rcx, 1
0x140009e99  jnz     short loc_140009E8F
0x140009e9b  mov     rcx, [rbx+8]
0x140009e9f  mov     rcx, [rcx]; psa
0x140009ea2  call    cs:__imp_SafeArrayUnaccessData
0x140009ea8  mov     rcx, [rbx+8]
0x140009eac  mov     rcx, [rcx]
0x140009eaf  add     rsp, 20h
0x140009eb3  pop     rbx
0x140009eb4  jmp     cs:__imp_SafeArrayDestroy
```
