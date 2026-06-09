# ErrorRecord::MakeDeepStringCopy(char * &,char const *,unsigned __int64)

- ea: `0x18001ae60`
- end: `0x18001aeed`
- name: `?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEADPEBD_K@Z`
- size: `141`
- prototype: `static void(char **, const char *, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001ac4c`
- `0x18001ad80`
- `0x18001afa8`
- `0x18001b068`

## callees

- `0x180011fc0`
- `0x180012c06`
- `0x18001ae24`
- `0x18001ae60`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001ae8b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ae8b`

## pseudocode

```c
void __fastcall ErrorRecord::MakeDeepStringCopy(char **a1, const char *a2)
{
  void *v4; // rcx
  __int64 v5; // rax
  size_t v6; // rsi
  void *v7; // r14

  v4 = *a1;
  if ( v4 )
  {
    operator delete(v4);
    *a1 = 0;
  }
  if ( a2 )
  {
    v5 = mlib::m_traits<char>::CStrlen(a2, 1023);
    if ( v5 )
    {
      v6 = v5 + 1;
      try
      {
        v7 = operator new[](v5 + 1);
        memcpy_0(v7, a2, v6);
        *a1 = (char *)v7;
      }
      catch ( mlib::CStringTooBig )
      {
        return;
      }
      catch ( std::bad_alloc )
      {
      }
    }
  }
}

```

## disassembly

```asm
0x18001ae60  mov     rax, rsp
0x18001ae63  push    r14
0x18001ae65  sub     rsp, 30h
0x18001ae69  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x18001ae71  mov     [rax+8], rbx
0x18001ae75  mov     [rax+10h], rsi
0x18001ae79  mov     [rax+18h], rdi
0x18001ae7d  mov     rbx, rdx
0x18001ae80  mov     rdi, rcx
0x18001ae83  mov     rcx, [rcx]
0x18001ae86  test    rcx, rcx
0x18001ae89  jz      short loc_18001AE9B
0x18001ae8b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ae92  nop     dword ptr [rax+rax+00h]
0x18001ae97  and     qword ptr [rdi], 0
0x18001ae9b  test    rbx, rbx
0x18001ae9e  jz      short loc_18001AED6
0x18001aea0  mov     edx, 3FFh
0x18001aea5  mov     rcx, rbx
0x18001aea8  call    ?CStrlen@?$m_traits@D@mlib@@SA_KPEBD_K@Z; mlib::m_traits<char>::CStrlen(char const *,unsigned __int64)
0x18001aead  test    rax, rax
0x18001aeb0  jz      short loc_18001AED6
0x18001aeb2  lea     rsi, [rax+1]
0x18001aeb6  mov     rcx, rsi; unsigned __int64
0x18001aeb9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001aebe  mov     r14, rax
0x18001aec1  mov     r8, rsi; Size
0x18001aec4  mov     rdx, rbx; Src
0x18001aec7  mov     rcx, rax; void *
0x18001aeca  call    memcpy_0
0x18001aecf  mov     [rdi], r14
0x18001aed2  jmp     short loc_18001AED6
0x18001aed4  jmp     short $+2
0x18001aed6  mov     rbx, [rsp+38h+arg_0]
0x18001aedb  mov     rsi, [rsp+38h+arg_8]
0x18001aee0  mov     rdi, [rsp+38h+arg_10]
0x18001aee5  add     rsp, 30h
0x18001aee9  pop     r14
0x18001aeeb  retn
```
