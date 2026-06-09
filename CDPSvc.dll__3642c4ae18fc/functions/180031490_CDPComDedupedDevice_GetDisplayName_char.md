# CDPComDedupedDevice::GetDisplayName(char * *)

- ea: `0x180031490`
- end: `0x180031510`
- name: `?GetDisplayName@CDPComDedupedDevice@@UEAAJPEAPEAD@Z`
- size: `128`
- prototype: `__int64 __fastcall(CDPComDedupedDevice *__hidden this, char **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ddf8`
- `0x180031490`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800314fd`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800314fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800314dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800314dc`

## string_xrefs

- `0x1800314be`: `.\cdpcomdedupeddevice.cpp`

## pseudocode

```c
__int64 __fastcall CDPComDedupedDevice::GetDisplayName(CDPComDedupedDevice *this, char **a2)
{
  char *v5; // rax
  const char *v6; // r8
  unsigned int v7; // [rsp+48h] [rbp+10h] BYREF
  int v8; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 )
  {
    v5 = (char *)CoTaskMemAlloc(*((_QWORD *)this + 9) + 1LL);
    *a2 = v5;
    v6 = (char *)this + 56;
    if ( *((_QWORD *)this + 10) > 0xFu )
      v6 = *(const char **)v6;
    strcpy_s(v5, *((_QWORD *)this + 9) + 1LL, v6);
    return 0;
  }
  else
  {
    v7 = -2147467261;
    v8 = 121;
    Log<long &,char const (&)[28],int>((__int64)this, 0, &v7, ".\\cdpcomdedupeddevice.cpp", &v8);
    return v7;
  }
}

```

## disassembly

```asm
0x180031490  mov     rax, rsp
0x180031493  mov     [rax+8], rbx
0x180031497  push    rdi
0x180031498  sub     rsp, 30h
0x18003149c  mov     rbx, rdx
0x18003149f  mov     rdi, rcx
0x1800314a2  test    rdx, rdx
0x1800314a5  jnz     short loc_1800314D5
0x1800314a7  mov     dword ptr [rax+10h], 80004003h
0x1800314ae  mov     dword ptr [rax+18h], 79h ; 'y'
0x1800314b5  lea     rax, [rax+18h]
0x1800314b9  mov     [rsp+38h+var_18], rax
0x1800314be  lea     r9, aCdpcomdedupedd; ".\\cdpcomdedupeddevice.cpp"
0x1800314c5  lea     r8, [rsp+38h+arg_8]
0x1800314ca  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x1800314cf  mov     eax, [rsp+38h+arg_8]
0x1800314d3  jmp     short loc_180031505
0x1800314d5  mov     rcx, [rcx+48h]
0x1800314d9  inc     rcx; cb
0x1800314dc  call    cs:__imp_CoTaskMemAlloc
0x1800314e2  mov     [rbx], rax
0x1800314e5  lea     r8, [rdi+38h]
0x1800314e9  cmp     qword ptr [r8+18h], 0Fh
0x1800314ee  jbe     short loc_1800314F3
0x1800314f0  mov     r8, [r8]; Source
0x1800314f3  mov     rdx, [rdi+48h]
0x1800314f7  inc     rdx; SizeInBytes
0x1800314fa  mov     rcx, rax; Destination
0x1800314fd  call    cs:__imp_strcpy_s
0x180031503  xor     eax, eax
0x180031505  mov     rbx, [rsp+38h+arg_0]
0x18003150a  add     rsp, 30h
0x18003150e  pop     rdi
0x18003150f  retn
```
