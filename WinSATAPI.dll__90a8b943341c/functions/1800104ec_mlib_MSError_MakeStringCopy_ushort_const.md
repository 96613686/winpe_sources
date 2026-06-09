# mlib::MSError::MakeStringCopy(ushort const *)

- ea: `0x1800104ec`
- end: `0x180010580`
- name: `?MakeStringCopy@MSError@mlib@@CAPEAGPEBG@Z`
- size: `148`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *Src)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b7c0`
- `0x18000c9a0`
- `0x1800104b4`
- `0x18001d3e0`
- `0x180030000`
- `0x180030c93`

## callees

- `0x180003640`
- `0x1800104ec`
- `0x180012c06`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010540`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010540`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001052c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001052c`

## pseudocode

```c
unsigned __int16 *__fastcall mlib::MSError::MakeStringCopy(const unsigned __int16 *Src)
{
  SIZE_T v2; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *result; // rax
  unsigned __int16 *v5; // rdi

  if ( !Src || *Src )
    return 0;
  try
  {
    v2 = 2 * mlib::m_traits<unsigned short>::CStrlen(Src, 0x10000) + 2;
    ProcessHeap = GetProcessHeap();
    result = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, v2);
    v5 = result;
    if ( result )
    {
      memcpy_0(result, Src, v2);
      result = v5;
    }
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800104ec  mov     rax, rsp
0x1800104ef  push    r14
0x1800104f1  sub     rsp, 30h
0x1800104f5  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x1800104fd  mov     [rax+8], rbx
0x180010501  mov     [rax+10h], rsi
0x180010505  mov     [rax+18h], rdi
0x180010509  mov     rbx, rcx
0x18001050c  xor     r14d, r14d
0x18001050f  test    rcx, rcx
0x180010512  jz      short loc_180010567
0x180010514  cmp     [rcx], r14w
0x180010518  jnz     short loc_180010567
0x18001051a  mov     edx, 10000h
0x18001051f  call    ?CStrlen@?$m_traits@G@mlib@@SA_KPEBG_K@Z; mlib::m_traits<ushort>::CStrlen(ushort const *,unsigned __int64)
0x180010524  lea     rsi, ds:2[rax*2]
0x18001052c  call    cs:__imp_GetProcessHeap
0x180010533  nop     dword ptr [rax+rax+00h]
0x180010538  mov     rcx, rax; hHeap
0x18001053b  mov     r8, rsi; dwBytes
0x18001053e  xor     edx, edx; dwFlags
0x180010540  call    cs:__imp_HeapAlloc
0x180010547  nop     dword ptr [rax+rax+00h]
0x18001054c  mov     rdi, rax
0x18001054f  test    rax, rax
0x180010552  jz      short loc_180010569
0x180010554  mov     r8, rsi; Size
0x180010557  mov     rdx, rbx; Src
0x18001055a  mov     rcx, rdi; void *
0x18001055d  call    memcpy_0
0x180010562  mov     rax, rdi
0x180010565  jmp     short loc_180010569
0x180010567  xor     eax, eax
0x180010569  mov     rbx, [rsp+38h+arg_0]
0x18001056e  mov     rsi, [rsp+38h+arg_8]
0x180010573  mov     rdi, [rsp+38h+arg_10]
0x180010578  add     rsp, 30h
0x18001057c  pop     r14
0x18001057e  retn
```
