# CScratchMediaSample::Release(void)

- ea: `0x18002ad70`
- end: `0x18002adb4`
- name: `?Release@CScratchMediaSample@@UEAAKXZ`
- size: `68`
- prototype: `unsigned int __fastcall(CScratchMediaSample *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x180001048`
- `0x18002ad70`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002ad99`
- `ole32!CoTaskMemFree` at `0x18002ad99`

## pseudocode

```c
__int64 __fastcall CScratchMediaSample::Release(CScratchMediaSample *this)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !(_DWORD)result )
  {
    if ( this )
    {
      *(_QWORD *)this = &CScratchMediaSample::`vftable';
      CoTaskMemFree(*((LPVOID *)this + 2));
      operator delete(this, 0x20u);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002ad70  push    rbx
0x18002ad72  sub     rsp, 20h
0x18002ad76  mov     rbx, rcx
0x18002ad79  or      eax, 0FFFFFFFFh
0x18002ad7c  lock xadd [rcx+8], eax
0x18002ad81  sub     eax, 1
0x18002ad84  jnz     short loc_18002ADAE
0x18002ad86  test    rcx, rcx
0x18002ad89  jz      short loc_18002ADAC
0x18002ad8b  lea     rax, ??_7CScratchMediaSample@@6B@; const CScratchMediaSample::`vftable'
0x18002ad92  mov     [rcx], rax
0x18002ad95  mov     rcx, [rcx+10h]; pv
0x18002ad99  call    cs:__imp_CoTaskMemFree
0x18002ad9f  mov     edx, 20h ; ' '; unsigned __int64
0x18002ada4  mov     rcx, rbx; void *
0x18002ada7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002adac  xor     eax, eax
0x18002adae  add     rsp, 20h
0x18002adb2  pop     rbx
0x18002adb3  retn
```
