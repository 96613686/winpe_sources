# CDPComDedupedDevice::GetRemoteUserDisplayName(char * *)

- ea: `0x180031770`
- end: `0x1800317f9`
- name: `?GetRemoteUserDisplayName@CDPComDedupedDevice@@UEAAJPEAPEAD@Z`
- size: `137`
- prototype: `__int64 __fastcall(CDPComDedupedDevice *__hidden this, char **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ddf8`
- `0x180031770`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800317e6`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800317e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800317bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800317bf`

## string_xrefs

- `0x18003179e`: `.\cdpcomdedupeddevice.cpp`

## pseudocode

```c
__int64 __fastcall CDPComDedupedDevice::GetRemoteUserDisplayName(CDPComDedupedDevice *this, char **a2)
{
  char *v5; // rax
  const char *v6; // r8
  unsigned int v7; // [rsp+48h] [rbp+10h] BYREF
  int v8; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 )
  {
    v5 = (char *)CoTaskMemAlloc(*((_QWORD *)this + 29) + 1LL);
    *a2 = v5;
    v6 = (char *)this + 216;
    if ( *((_QWORD *)this + 30) > 0xFu )
      v6 = *(const char **)v6;
    strcpy_s(v5, *((_QWORD *)this + 29) + 1LL, v6);
    return 0;
  }
  else
  {
    v7 = -2147467261;
    v8 = 265;
    Log<long &,char const (&)[28],int>((__int64)this, 0, &v7, ".\\cdpcomdedupeddevice.cpp", &v8);
    return v7;
  }
}

```

## disassembly

```asm
0x180031770  mov     rax, rsp
0x180031773  mov     [rax+8], rbx
0x180031777  push    rdi
0x180031778  sub     rsp, 30h
0x18003177c  mov     rbx, rdx
0x18003177f  mov     rdi, rcx
0x180031782  test    rdx, rdx
0x180031785  jnz     short loc_1800317B5
0x180031787  mov     dword ptr [rax+10h], 80004003h
0x18003178e  mov     dword ptr [rax+18h], 109h
0x180031795  lea     rax, [rax+18h]
0x180031799  mov     [rsp+38h+var_18], rax
0x18003179e  lea     r9, aCdpcomdedupedd; ".\\cdpcomdedupeddevice.cpp"
0x1800317a5  lea     r8, [rsp+38h+arg_8]
0x1800317aa  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x1800317af  mov     eax, [rsp+38h+arg_8]
0x1800317b3  jmp     short loc_1800317EE
0x1800317b5  mov     rcx, [rcx+0E8h]
0x1800317bc  inc     rcx; cb
0x1800317bf  call    cs:__imp_CoTaskMemAlloc
0x1800317c5  mov     [rbx], rax
0x1800317c8  lea     r8, [rdi+0D8h]
0x1800317cf  cmp     qword ptr [r8+18h], 0Fh
0x1800317d4  jbe     short loc_1800317D9
0x1800317d6  mov     r8, [r8]; Source
0x1800317d9  mov     rdx, [rdi+0E8h]
0x1800317e0  inc     rdx; SizeInBytes
0x1800317e3  mov     rcx, rax; Destination
0x1800317e6  call    cs:__imp_strcpy_s
0x1800317ec  xor     eax, eax
0x1800317ee  mov     rbx, [rsp+38h+arg_0]
0x1800317f3  add     rsp, 30h
0x1800317f7  pop     rdi
0x1800317f8  retn
```
