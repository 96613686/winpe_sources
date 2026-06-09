# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x40a986`
- end: `0x40a9bd`
- name: `?GetLastErrorFail@details@wil@@YGKPAXIPBD110@Z`
- size: `55`
- prototype: `DWORD __userpurge@<eax>(int@<edx>, int@<ecx>, wil::details *this, void *, unsigned int, const char *, const char *, const char *, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x40a9c3`
- `0x40ad9c`
- `0x40bf6f`

## callees

- `0x40a986`
- `0x40bb71`

## import_xrefs

- `KERNEL32!GetLastError` at `0x40a991`
- `KERNEL32!GetLastError` at `0x40a991`

## pseudocode

```c
DWORD __userpurge wil::details::GetLastErrorFail@<eax>(
        int a1@<edx>,
        int a2@<ecx>,
        wil::details *this,
        void *a4,
        unsigned int a5,
        const char *a6,
        const char *a7,
        const char *a8,
        void *a9)
{
  DWORD result; // eax
  int v12; // ecx

  result = GetLastError();
  if ( !result )
  {
    wil::details::ReportFailure_Hr<2>(a2, a1, this, 0, 0, a6, -2147024228, v12);
    return 668;
  }
  return result;
}

```

## disassembly

```asm
0x40a986  mov     edi, edi
0x40a988  push    ebp
0x40a989  mov     ebp, esp
0x40a98b  push    esi
0x40a98c  push    edi
0x40a98d  mov     esi, edx
0x40a98f  mov     edi, ecx
0x40a991  call    ds:__imp__GetLastError@0; GetLastError()
0x40a997  test    eax, eax
0x40a999  jnz     short loc_40A9B7
0x40a99b  push    ecx
0x40a99c  push    8007029Ch
0x40a9a1  push    [ebp+arg_C]
0x40a9a4  mov     edx, esi
0x40a9a6  mov     ecx, edi
0x40a9a8  push    eax
0x40a9a9  push    eax
0x40a9aa  push    [ebp+this]
0x40a9ad  call    ??$ReportFailure_Hr@$01@details@wil@@YGXPAXIPBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x40a9b2  mov     eax, 29Ch
0x40a9b7  pop     edi
0x40a9b8  pop     esi
0x40a9b9  pop     ebp
0x40a9ba  retn    10h
```
