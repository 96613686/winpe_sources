# PathMatchesApplication(char *)

- ea: `0x1800014a0`
- end: `0x180001566`
- name: `?PathMatchesApplication@@YAHPEAD@Z`
- size: `198`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800011e0`

## callees

- `0x180001430`
- `0x1800014a0`
- `0x180003100`
- `0x1800036e8`
- `0x180003748`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x18000154c`
- `KERNEL32!lstrlenA` at `0x18000154c`

## pseudocode

```c
__int64 __fastcall PathMatchesApplication(char *a1)
{
  const char **v2; // rsi
  unsigned int v3; // edi
  __int64 result; // rax

  if ( dword_180007184 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180007184);
    if ( dword_180007184 == -1 )
    {
      dword_180007180 = lstrlenA("/app_");
      Init_thread_footer(&dword_180007184);
    }
  }
LABEL_6:
  result = (__int64)stristr(a1, "/app_");
  if ( result )
  {
    v2 = (const char **)&g_forbidden_dir_tails;
    a1 = (char *)(result + dword_180007180);
    v3 = 0;
    while ( !(unsigned int)PathMatches(a1, *v2) )
    {
      ++v3;
      ++v2;
      if ( v3 >= 6 )
        goto LABEL_6;
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800014a0  mov     [rsp+arg_0], rbx
0x1800014a5  mov     [rsp+arg_8], rsi
0x1800014aa  push    rdi
0x1800014ab  sub     rsp, 20h
0x1800014af  mov     rax, gs:58h
0x1800014b8  mov     rbx, rcx
0x1800014bb  mov     edx, cs:_tls_index
0x1800014c1  mov     ecx, 4
0x1800014c6  mov     r8, [rax+rdx*8]
0x1800014ca  mov     eax, [rcx+r8]
0x1800014ce  cmp     cs:dword_180007184, eax
0x1800014d4  jg      short loc_180001530
0x1800014d6  jmp     short loc_180001505
0x1800014d8  movsxd  rbx, cs:dword_180007180
0x1800014df  lea     rsi, ?g_forbidden_dir_tails@@3PAPEADA; char * near * g_forbidden_dir_tails
0x1800014e6  add     rbx, rax
0x1800014e9  xor     edi, edi
0x1800014eb  mov     rdx, [rsi]; String2
0x1800014ee  mov     rcx, rbx; String1
0x1800014f1  call    ?PathMatches@@YAHPEBD0@Z; PathMatches(char const *,char const *)
0x1800014f6  test    eax, eax
0x1800014f8  jnz     short loc_180001529
0x1800014fa  inc     edi
0x1800014fc  add     rsi, 8
0x180001500  cmp     edi, 6
0x180001503  jb      short loc_1800014EB
0x180001505  lea     rdx, String; "/app_"
0x18000150c  mov     rcx, rbx; char *
0x18000150f  call    ?stristr@@YAPEADPEAD0@Z; stristr(char *,char *)
0x180001514  test    rax, rax
0x180001517  jnz     short loc_1800014D8
0x180001519  mov     rbx, [rsp+28h+arg_0]
0x18000151e  mov     rsi, [rsp+28h+arg_8]
0x180001523  add     rsp, 20h
0x180001527  pop     rdi
0x180001528  retn
0x180001529  mov     eax, 1
0x18000152e  jmp     short loc_180001519
0x180001530  lea     rcx, dword_180007184
0x180001537  call    _Init_thread_header
0x18000153c  cmp     cs:dword_180007184, 0FFFFFFFFh
0x180001543  jnz     short loc_180001505
0x180001545  lea     rcx, String; "/app_"
0x18000154c  call    cs:__imp_lstrlenA
0x180001552  lea     rcx, dword_180007184
0x180001559  mov     cs:dword_180007180, eax
0x18000155f  call    _Init_thread_footer
0x180001564  jmp     short loc_180001505
```
