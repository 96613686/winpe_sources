# CDPComDedupedDevice::GetRemoteUserEmail(char * *)

- ea: `0x180031800`
- end: `0x180031889`
- name: `?GetRemoteUserEmail@CDPComDedupedDevice@@UEAAJPEAPEAD@Z`
- size: `137`
- prototype: `__int64 __fastcall(CDPComDedupedDevice *__hidden this, char **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ddf8`
- `0x180031800`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180031876`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180031876`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003184f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003184f`

## string_xrefs

- `0x18003182e`: `.\cdpcomdedupeddevice.cpp`

## pseudocode

```c
__int64 __fastcall CDPComDedupedDevice::GetRemoteUserEmail(CDPComDedupedDevice *this, char **a2)
{
  char *v5; // rax
  const char *v6; // r8
  unsigned int v7; // [rsp+48h] [rbp+10h] BYREF
  int v8; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 )
  {
    v5 = (char *)CoTaskMemAlloc(*((_QWORD *)this + 33) + 1LL);
    *a2 = v5;
    v6 = (char *)this + 248;
    if ( *((_QWORD *)this + 34) > 0xFu )
      v6 = *(const char **)v6;
    strcpy_s(v5, *((_QWORD *)this + 33) + 1LL, v6);
    return 0;
  }
  else
  {
    v7 = -2147467261;
    v8 = 279;
    Log<long &,char const (&)[28],int>((__int64)this, 0, &v7, ".\\cdpcomdedupeddevice.cpp", &v8);
    return v7;
  }
}

```

## disassembly

```asm
0x180031800  mov     rax, rsp
0x180031803  mov     [rax+8], rbx
0x180031807  push    rdi
0x180031808  sub     rsp, 30h
0x18003180c  mov     rbx, rdx
0x18003180f  mov     rdi, rcx
0x180031812  test    rdx, rdx
0x180031815  jnz     short loc_180031845
0x180031817  mov     dword ptr [rax+10h], 80004003h
0x18003181e  mov     dword ptr [rax+18h], 117h
0x180031825  lea     rax, [rax+18h]
0x180031829  mov     [rsp+38h+var_18], rax
0x18003182e  lea     r9, aCdpcomdedupedd; ".\\cdpcomdedupeddevice.cpp"
0x180031835  lea     r8, [rsp+38h+arg_8]
0x18003183a  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x18003183f  mov     eax, [rsp+38h+arg_8]
0x180031843  jmp     short loc_18003187E
0x180031845  mov     rcx, [rcx+108h]
0x18003184c  inc     rcx; cb
0x18003184f  call    cs:__imp_CoTaskMemAlloc
0x180031855  mov     [rbx], rax
0x180031858  lea     r8, [rdi+0F8h]
0x18003185f  cmp     qword ptr [r8+18h], 0Fh
0x180031864  jbe     short loc_180031869
0x180031866  mov     r8, [r8]; Source
0x180031869  mov     rdx, [rdi+108h]
0x180031870  inc     rdx; SizeInBytes
0x180031873  mov     rcx, rax; Destination
0x180031876  call    cs:__imp_strcpy_s
0x18003187c  xor     eax, eax
0x18003187e  mov     rbx, [rsp+38h+arg_0]
0x180031883  add     rsp, 30h
0x180031887  pop     rdi
0x180031888  retn
```
