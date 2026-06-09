# LoadStringFromResource(uint,ushort * *)

- ea: `0x18000af88`
- end: `0x18000b007`
- name: `?LoadStringFromResource@@YAJIPEAPEAG@Z`
- size: `127`
- prototype: `__int64 __fastcall(UINT uID, LPWSTR *ppwsz)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000aa80`
- `0x18000ab70`

## callees

- `0x18000af88`
- `0x18000b630`

## import_xrefs

- `USER32!LoadStringW` at `0x18000afca`
- `USER32!LoadStringW` at `0x18000afca`
- `SHLWAPI!SHStrDupW` at `0x18000afdc`
- `SHLWAPI!SHStrDupW` at `0x18000afdc`

## pseudocode

```c
__int64 __fastcall LoadStringFromResource(UINT uID, LPWSTR *ppwsz)
{
  unsigned int v3; // ebx
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  *ppwsz = 0;
  v3 = -2147467259;
  if ( LoadStringW(g_hInst, uID, Buffer, 260) )
    return (unsigned int)SHStrDupW(Buffer, ppwsz);
  return v3;
}

```

## disassembly

```asm
0x18000af88  mov     [rsp+arg_10], rbx
0x18000af8d  push    rdi
0x18000af8e  sub     rsp, 240h
0x18000af95  mov     rax, cs:__security_cookie
0x18000af9c  xor     rax, rsp
0x18000af9f  mov     [rsp+248h+var_18], rax
0x18000afa7  mov     rdi, rdx
0x18000afaa  mov     qword ptr [rdx], 0
0x18000afb1  mov     edx, ecx; uID
0x18000afb3  lea     r8, [rsp+248h+Buffer]; lpBuffer
0x18000afb8  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000afbf  mov     r9d, 104h; cchBufferMax
0x18000afc5  mov     ebx, 80004005h
0x18000afca  call    cs:__imp_LoadStringW
0x18000afd0  test    eax, eax
0x18000afd2  jz      short loc_18000AFE4
0x18000afd4  mov     rdx, rdi; ppwsz
0x18000afd7  lea     rcx, [rsp+248h+Buffer]; psz
0x18000afdc  call    cs:__imp_SHStrDupW
0x18000afe2  mov     ebx, eax
0x18000afe4  mov     eax, ebx
0x18000afe6  mov     rcx, [rsp+248h+var_18]
0x18000afee  xor     rcx, rsp; StackCookie
0x18000aff1  call    __security_check_cookie
0x18000aff6  mov     rbx, [rsp+248h+arg_10]
0x18000affe  add     rsp, 240h
0x18000b005  pop     rdi
0x18000b006  retn
```
