# CDPComDedupedDevice::GetRemoteUserFirstName(char * *)

- ea: `0x180031890`
- end: `0x180031919`
- name: `?GetRemoteUserFirstName@CDPComDedupedDevice@@UEAAJPEAPEAD@Z`
- size: `137`
- prototype: `__int64 __fastcall(CDPComDedupedDevice *__hidden this, char **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ddf8`
- `0x180031890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180031906`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180031906`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800318df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800318df`

## string_xrefs

- `0x1800318be`: `.\cdpcomdedupeddevice.cpp`

## pseudocode

```c
__int64 __fastcall CDPComDedupedDevice::GetRemoteUserFirstName(CDPComDedupedDevice *this, char **a2)
{
  char *v5; // rax
  const char *v6; // r8
  unsigned int v7; // [rsp+48h] [rbp+10h] BYREF
  int v8; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 )
  {
    v5 = (char *)CoTaskMemAlloc(*((_QWORD *)this + 21) + 1LL);
    *a2 = v5;
    v6 = (char *)this + 152;
    if ( *((_QWORD *)this + 22) > 0xFu )
      v6 = *(const char **)v6;
    strcpy_s(v5, *((_QWORD *)this + 21) + 1LL, v6);
    return 0;
  }
  else
  {
    v7 = -2147467261;
    v8 = 237;
    Log<long &,char const (&)[28],int>((__int64)this, 0, &v7, ".\\cdpcomdedupeddevice.cpp", &v8);
    return v7;
  }
}

```

## disassembly

```asm
0x180031890  mov     rax, rsp
0x180031893  mov     [rax+8], rbx
0x180031897  push    rdi
0x180031898  sub     rsp, 30h
0x18003189c  mov     rbx, rdx
0x18003189f  mov     rdi, rcx
0x1800318a2  test    rdx, rdx
0x1800318a5  jnz     short loc_1800318D5
0x1800318a7  mov     dword ptr [rax+10h], 80004003h
0x1800318ae  mov     dword ptr [rax+18h], 0EDh
0x1800318b5  lea     rax, [rax+18h]
0x1800318b9  mov     [rsp+38h+var_18], rax
0x1800318be  lea     r9, aCdpcomdedupedd; ".\\cdpcomdedupeddevice.cpp"
0x1800318c5  lea     r8, [rsp+38h+arg_8]
0x1800318ca  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x1800318cf  mov     eax, [rsp+38h+arg_8]
0x1800318d3  jmp     short loc_18003190E
0x1800318d5  mov     rcx, [rcx+0A8h]
0x1800318dc  inc     rcx; cb
0x1800318df  call    cs:__imp_CoTaskMemAlloc
0x1800318e5  mov     [rbx], rax
0x1800318e8  lea     r8, [rdi+98h]
0x1800318ef  cmp     qword ptr [r8+18h], 0Fh
0x1800318f4  jbe     short loc_1800318F9
0x1800318f6  mov     r8, [r8]; Source
0x1800318f9  mov     rdx, [rdi+0A8h]
0x180031900  inc     rdx; SizeInBytes
0x180031903  mov     rcx, rax; Destination
0x180031906  call    cs:__imp_strcpy_s
0x18003190c  xor     eax, eax
0x18003190e  mov     rbx, [rsp+38h+arg_0]
0x180031913  add     rsp, 30h
0x180031917  pop     rdi
0x180031918  retn
```
