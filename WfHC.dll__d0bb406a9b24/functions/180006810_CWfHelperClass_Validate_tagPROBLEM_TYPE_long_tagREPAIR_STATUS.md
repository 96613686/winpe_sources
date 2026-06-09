# CWfHelperClass::Validate(tagPROBLEM_TYPE,long *,tagREPAIR_STATUS *)

- ea: `0x180006810`
- end: `0x180006823`
- name: `?Validate@CWfHelperClass@@UEAAJW4tagPROBLEM_TYPE@@PEAJPEAW4tagREPAIR_STATUS@@@Z`
- size: `19`
- prototype: `__int64 __fastcall(CWfHelperClass *__hidden this, enum tagPROBLEM_TYPE, int *, enum tagREPAIR_STATUS *)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
__int64 __fastcall CWfHelperClass::Validate(
        CWfHelperClass *this,
        enum tagPROBLEM_TYPE a2,
        int *a3,
        enum tagREPAIR_STATUS *a4)
{
  *a4 = (*((_DWORD *)this + 43) != 0) + 1;
  return 0;
}

```

## disassembly

```asm
0x180006810  xor     eax, eax
0x180006812  cmp     [rcx+0ACh], eax
0x180006818  setnz   al
0x18000681b  inc     eax
0x18000681d  mov     [r9], eax
0x180006820  xor     eax, eax
0x180006822  retn
```
