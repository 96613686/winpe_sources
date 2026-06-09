# CDPComDedupedDevice::GetId(char * *)

- ea: `0x180031520`
- end: `0x1800315a0`
- name: `?GetId@CDPComDedupedDevice@@UEAAJPEAPEAD@Z`
- size: `128`
- prototype: `__int64 __fastcall(CDPComDedupedDevice *__hidden this, char **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ddf8`
- `0x180031520`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18003158d`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18003158d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003156c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003156c`

## string_xrefs

- `0x18003154e`: `.\cdpcomdedupeddevice.cpp`

## pseudocode

```c
__int64 __fastcall CDPComDedupedDevice::GetId(CDPComDedupedDevice *this, char **a2)
{
  char *v5; // rax
  const char *v6; // r8
  unsigned int v7; // [rsp+48h] [rbp+10h] BYREF
  int v8; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 )
  {
    v5 = (char *)CoTaskMemAlloc(*((_QWORD *)this + 5) + 1LL);
    *a2 = v5;
    v6 = (char *)this + 24;
    if ( *((_QWORD *)this + 6) > 0xFu )
      v6 = *(const char **)v6;
    strcpy_s(v5, *((_QWORD *)this + 5) + 1LL, v6);
    return 0;
  }
  else
  {
    v7 = -2147467261;
    v8 = 107;
    Log<long &,char const (&)[28],int>((__int64)this, 0, &v7, ".\\cdpcomdedupeddevice.cpp", &v8);
    return v7;
  }
}

```

## disassembly

```asm
0x180031520  mov     rax, rsp
0x180031523  mov     [rax+8], rbx
0x180031527  push    rdi
0x180031528  sub     rsp, 30h
0x18003152c  mov     rbx, rdx
0x18003152f  mov     rdi, rcx
0x180031532  test    rdx, rdx
0x180031535  jnz     short loc_180031565
0x180031537  mov     dword ptr [rax+10h], 80004003h
0x18003153e  mov     dword ptr [rax+18h], 6Bh ; 'k'
0x180031545  lea     rax, [rax+18h]
0x180031549  mov     [rsp+38h+var_18], rax
0x18003154e  lea     r9, aCdpcomdedupedd; ".\\cdpcomdedupeddevice.cpp"
0x180031555  lea     r8, [rsp+38h+arg_8]
0x18003155a  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x18003155f  mov     eax, [rsp+38h+arg_8]
0x180031563  jmp     short loc_180031595
0x180031565  mov     rcx, [rcx+28h]
0x180031569  inc     rcx; cb
0x18003156c  call    cs:__imp_CoTaskMemAlloc
0x180031572  mov     [rbx], rax
0x180031575  lea     r8, [rdi+18h]
0x180031579  cmp     qword ptr [r8+18h], 0Fh
0x18003157e  jbe     short loc_180031583
0x180031580  mov     r8, [r8]; Source
0x180031583  mov     rdx, [rdi+28h]
0x180031587  inc     rdx; SizeInBytes
0x18003158a  mov     rcx, rax; Destination
0x18003158d  call    cs:__imp_strcpy_s
0x180031593  xor     eax, eax
0x180031595  mov     rbx, [rsp+38h+arg_0]
0x18003159a  add     rsp, 30h
0x18003159e  pop     rdi
0x18003159f  retn
```
