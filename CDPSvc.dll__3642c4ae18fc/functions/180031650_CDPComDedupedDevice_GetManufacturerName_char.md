# CDPComDedupedDevice::GetManufacturerName(char * *)

- ea: `0x180031650`
- end: `0x1800316d0`
- name: `?GetManufacturerName@CDPComDedupedDevice@@UEAAJPEAPEAD@Z`
- size: `128`
- prototype: `__int64 __fastcall(CDPComDedupedDevice *__hidden this, char **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ddf8`
- `0x180031650`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800316bd`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800316bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003169c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003169c`

## string_xrefs

- `0x18003167e`: `.\cdpcomdedupeddevice.cpp`

## pseudocode

```c
__int64 __fastcall CDPComDedupedDevice::GetManufacturerName(CDPComDedupedDevice *this, char **a2)
{
  char *v5; // rax
  const char *v6; // r8
  unsigned int v7; // [rsp+48h] [rbp+10h] BYREF
  int v8; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 )
  {
    v5 = (char *)CoTaskMemAlloc(*((_QWORD *)this + 13) + 1LL);
    *a2 = v5;
    v6 = (char *)this + 88;
    if ( *((_QWORD *)this + 14) > 0xFu )
      v6 = *(const char **)v6;
    strcpy_s(v5, *((_QWORD *)this + 13) + 1LL, v6);
    return 0;
  }
  else
  {
    v7 = -2147467261;
    v8 = 135;
    Log<long &,char const (&)[28],int>((__int64)this, 0, &v7, ".\\cdpcomdedupeddevice.cpp", &v8);
    return v7;
  }
}

```

## disassembly

```asm
0x180031650  mov     rax, rsp
0x180031653  mov     [rax+8], rbx
0x180031657  push    rdi
0x180031658  sub     rsp, 30h
0x18003165c  mov     rbx, rdx
0x18003165f  mov     rdi, rcx
0x180031662  test    rdx, rdx
0x180031665  jnz     short loc_180031695
0x180031667  mov     dword ptr [rax+10h], 80004003h
0x18003166e  mov     dword ptr [rax+18h], 87h
0x180031675  lea     rax, [rax+18h]
0x180031679  mov     [rsp+38h+var_18], rax
0x18003167e  lea     r9, aCdpcomdedupedd; ".\\cdpcomdedupeddevice.cpp"
0x180031685  lea     r8, [rsp+38h+arg_8]
0x18003168a  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x18003168f  mov     eax, [rsp+38h+arg_8]
0x180031693  jmp     short loc_1800316C5
0x180031695  mov     rcx, [rcx+68h]
0x180031699  inc     rcx; cb
0x18003169c  call    cs:__imp_CoTaskMemAlloc
0x1800316a2  mov     [rbx], rax
0x1800316a5  lea     r8, [rdi+58h]
0x1800316a9  cmp     qword ptr [r8+18h], 0Fh
0x1800316ae  jbe     short loc_1800316B3
0x1800316b0  mov     r8, [r8]; Source
0x1800316b3  mov     rdx, [rdi+68h]
0x1800316b7  inc     rdx; SizeInBytes
0x1800316ba  mov     rcx, rax; Destination
0x1800316bd  call    cs:__imp_strcpy_s
0x1800316c3  xor     eax, eax
0x1800316c5  mov     rbx, [rsp+38h+arg_0]
0x1800316ca  add     rsp, 30h
0x1800316ce  pop     rdi
0x1800316cf  retn
```
