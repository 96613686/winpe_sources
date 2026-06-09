# QueryPathOfRegTypeLibInternal

- ea: `0x180042130`
- end: `0x180042241`
- name: `QueryPathOfRegTypeLibInternal`
- size: `273`
- prototype: `__int64 __usercall@<rax>(GUID *rguid@<rcx>, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180042100`

## callees

- `0x180014840`
- `0x1800161b8`
- `0x180042130`
- `0x18004d900`
- `0x18004e530`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800421b7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800421b7`

## string_xrefs

- `0x18004217c`: `mincore\com\oleaut32\typelib\tlibapi.cpp`

## pseudocode

```c
__int64 __fastcall QueryPathOfRegTypeLibInternal(
        GUID *rguid,
        unsigned __int16 a2,
        unsigned __int16 a3,
        unsigned int a4,
        int a5,
        BSTR *a6)
{
  int RegTypeLibOfSzGuid_WithSyskind; // ebx
  __int64 v11; // rdx
  BOOL v13; // eax
  int v14; // [rsp+20h] [rbp-B8h]
  ITypeLib sz[10]; // [rsp+50h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  if ( !a6 )
  {
    RegTypeLibOfSzGuid_WithSyskind = -2147024809;
    v11 = 2887;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"mincore\\com\\oleaut32\\typelib\\tlibapi.cpp",
      (const char *)(unsigned int)RegTypeLibOfSzGuid_WithSyskind,
      v14);
    return (unsigned int)RegTypeLibOfSzGuid_WithSyskind;
  }
  *a6 = 0;
  memset_0(sz, 0, 0x4Eu);
  StringFromGUID2(rguid, (LPOLESTR)sz, 39);
  v13 = a2 == 0xFFFF && a3 == 0xFFFF;
  RegTypeLibOfSzGuid_WithSyskind = LoadRegTypeLibOfSzGuid_WithSyskind(sz, a2, a3, a4, v13, a6, 0, 0, a5 < 0);
  if ( RegTypeLibOfSzGuid_WithSyskind < 0 )
  {
    v11 = 2903;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180042130  push    rbx
0x180042132  push    rbp
0x180042133  push    rsi
0x180042134  push    rdi
0x180042135  push    r14
0x180042137  sub     rsp, 0B0h
0x18004213e  mov     rax, cs:__security_cookie
0x180042145  xor     rax, rsp
0x180042148  mov     [rsp+0D8h+var_38], rax
0x180042150  mov     rdi, [rsp+0D8h+arg_28]
0x180042158  mov     r14d, r9d
0x18004215b  movzx   ebx, r8w
0x18004215f  movzx   esi, dx
0x180042162  mov     rbp, rcx
0x180042165  test    rdi, rdi
0x180042168  jnz     short loc_180042192
0x18004216a  mov     ebx, 80070057h
0x18004216f  mov     edx, 0B47h; void *
0x180042174  mov     rcx, [rsp+0D8h]; this
0x18004217c  lea     r8, aMincoreComOlea_3; "mincore\\com\\oleaut32\\typelib\\tlibap"...
0x180042183  mov     r9d, ebx; char *
0x180042186  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004218b  mov     eax, ebx
0x18004218d  jmp     loc_180042223
0x180042192  xor     edx, edx; Val
0x180042194  mov     qword ptr [rdi], 0
0x18004219b  lea     rcx, [rsp+0D8h+sz]; void *
0x1800421a0  lea     r8d, [rdx+4Eh]; Size
0x1800421a4  call    memset_0
0x1800421a9  mov     r8d, 27h ; '''; cchMax
0x1800421af  lea     rdx, [rsp+0D8h+sz]; lpsz
0x1800421b4  mov     rcx, rbp; rguid
0x1800421b7  call    cs:__imp_StringFromGUID2
0x1800421bd  mov     ecx, [rsp+0D8h+arg_20]
0x1800421c4  mov     eax, 0FFFFh
0x1800421c9  shr     ecx, 1Fh
0x1800421cc  cmp     si, ax
0x1800421cf  jnz     short loc_1800421DD
0x1800421d1  cmp     bx, ax
0x1800421d4  jnz     short loc_1800421DD
0x1800421d6  mov     eax, 1
0x1800421db  jmp     short loc_1800421DF
0x1800421dd  xor     eax, eax
0x1800421df  mov     [rsp+0D8h+var_98], cl
0x1800421e3  mov     r9d, r14d
0x1800421e6  mov     [rsp+0D8h+var_A0], 0
0x1800421ef  lea     rcx, [rsp+0D8h+sz]
0x1800421f4  mov     [rsp+0D8h+var_A8], 0
0x1800421fc  movzx   r8d, bx
0x180042200  mov     [rsp+0D8h+var_B0], rdi
0x180042205  movzx   edx, si
0x180042208  mov     [rsp+0D8h+var_B8], eax
0x18004220c  call    LoadRegTypeLibOfSzGuid_WithSyskind
0x180042211  mov     ebx, eax
0x180042213  test    eax, eax
0x180042215  jns     short loc_180042221
0x180042217  mov     edx, 0B57h
0x18004221c  jmp     loc_180042174
0x180042221  xor     eax, eax
0x180042223  mov     rcx, [rsp+0D8h+var_38]
0x18004222b  xor     rcx, rsp; StackCookie
0x18004222e  call    __security_check_cookie
0x180042233  add     rsp, 0B0h
0x18004223a  pop     r14
0x18004223c  pop     rdi
0x18004223d  pop     rsi
0x18004223e  pop     rbp
0x18004223f  pop     rbx
0x180042240  retn
```
