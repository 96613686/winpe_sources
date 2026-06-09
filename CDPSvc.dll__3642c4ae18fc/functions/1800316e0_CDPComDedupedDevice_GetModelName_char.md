# CDPComDedupedDevice::GetModelName(char * *)

- ea: `0x1800316e0`
- end: `0x180031766`
- name: `?GetModelName@CDPComDedupedDevice@@UEAAJPEAPEAD@Z`
- size: `134`
- prototype: `__int64 __fastcall(CDPComDedupedDevice *__hidden this, char **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ddf8`
- `0x1800316e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180031753`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180031753`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003172f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003172f`

## string_xrefs

- `0x18003170e`: `.\cdpcomdedupeddevice.cpp`

## pseudocode

```c
__int64 __fastcall CDPComDedupedDevice::GetModelName(CDPComDedupedDevice *this, char **a2)
{
  char *v5; // rax
  const char *v6; // r8
  unsigned int v7; // [rsp+48h] [rbp+10h] BYREF
  int v8; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 )
  {
    v5 = (char *)CoTaskMemAlloc(*((_QWORD *)this + 17) + 1LL);
    *a2 = v5;
    v6 = (char *)this + 120;
    if ( *((_QWORD *)this + 18) > 0xFu )
      v6 = *(const char **)v6;
    strcpy_s(v5, *((_QWORD *)this + 17) + 1LL, v6);
    return 0;
  }
  else
  {
    v7 = -2147467261;
    v8 = 149;
    Log<long &,char const (&)[28],int>((__int64)this, 0, &v7, ".\\cdpcomdedupeddevice.cpp", &v8);
    return v7;
  }
}

```

## disassembly

```asm
0x1800316e0  mov     rax, rsp
0x1800316e3  mov     [rax+8], rbx
0x1800316e7  push    rdi
0x1800316e8  sub     rsp, 30h
0x1800316ec  mov     rbx, rdx
0x1800316ef  mov     rdi, rcx
0x1800316f2  test    rdx, rdx
0x1800316f5  jnz     short loc_180031725
0x1800316f7  mov     dword ptr [rax+10h], 80004003h
0x1800316fe  mov     dword ptr [rax+18h], 95h
0x180031705  lea     rax, [rax+18h]
0x180031709  mov     [rsp+38h+var_18], rax
0x18003170e  lea     r9, aCdpcomdedupedd; ".\\cdpcomdedupeddevice.cpp"
0x180031715  lea     r8, [rsp+38h+arg_8]
0x18003171a  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x18003171f  mov     eax, [rsp+38h+arg_8]
0x180031723  jmp     short loc_18003175B
0x180031725  mov     rcx, [rcx+88h]
0x18003172c  inc     rcx; cb
0x18003172f  call    cs:__imp_CoTaskMemAlloc
0x180031735  mov     [rbx], rax
0x180031738  lea     r8, [rdi+78h]
0x18003173c  cmp     qword ptr [r8+18h], 0Fh
0x180031741  jbe     short loc_180031746
0x180031743  mov     r8, [r8]; Source
0x180031746  mov     rdx, [rdi+88h]
0x18003174d  inc     rdx; SizeInBytes
0x180031750  mov     rcx, rax; Destination
0x180031753  call    cs:__imp_strcpy_s
0x180031759  xor     eax, eax
0x18003175b  mov     rbx, [rsp+38h+arg_0]
0x180031760  add     rsp, 30h
0x180031764  pop     rdi
0x180031765  retn
```
