# CDPComDedupedDevice::GetRemoteUserLastName(char * *)

- ea: `0x180031920`
- end: `0x1800319a9`
- name: `?GetRemoteUserLastName@CDPComDedupedDevice@@UEAAJPEAPEAD@Z`
- size: `137`
- prototype: `__int64 __fastcall(CDPComDedupedDevice *__hidden this, char **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ddf8`
- `0x180031920`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180031996`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180031996`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003196f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003196f`

## string_xrefs

- `0x18003194e`: `.\cdpcomdedupeddevice.cpp`

## pseudocode

```c
__int64 __fastcall CDPComDedupedDevice::GetRemoteUserLastName(CDPComDedupedDevice *this, char **a2)
{
  char *v5; // rax
  const char *v6; // r8
  unsigned int v7; // [rsp+48h] [rbp+10h] BYREF
  int v8; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 )
  {
    v5 = (char *)CoTaskMemAlloc(*((_QWORD *)this + 25) + 1LL);
    *a2 = v5;
    v6 = (char *)this + 184;
    if ( *((_QWORD *)this + 26) > 0xFu )
      v6 = *(const char **)v6;
    strcpy_s(v5, *((_QWORD *)this + 25) + 1LL, v6);
    return 0;
  }
  else
  {
    v7 = -2147467261;
    v8 = 251;
    Log<long &,char const (&)[28],int>((__int64)this, 0, &v7, ".\\cdpcomdedupeddevice.cpp", &v8);
    return v7;
  }
}

```

## disassembly

```asm
0x180031920  mov     rax, rsp
0x180031923  mov     [rax+8], rbx
0x180031927  push    rdi
0x180031928  sub     rsp, 30h
0x18003192c  mov     rbx, rdx
0x18003192f  mov     rdi, rcx
0x180031932  test    rdx, rdx
0x180031935  jnz     short loc_180031965
0x180031937  mov     dword ptr [rax+10h], 80004003h
0x18003193e  mov     dword ptr [rax+18h], 0FBh
0x180031945  lea     rax, [rax+18h]
0x180031949  mov     [rsp+38h+var_18], rax
0x18003194e  lea     r9, aCdpcomdedupedd; ".\\cdpcomdedupeddevice.cpp"
0x180031955  lea     r8, [rsp+38h+arg_8]
0x18003195a  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x18003195f  mov     eax, [rsp+38h+arg_8]
0x180031963  jmp     short loc_18003199E
0x180031965  mov     rcx, [rcx+0C8h]
0x18003196c  inc     rcx; cb
0x18003196f  call    cs:__imp_CoTaskMemAlloc
0x180031975  mov     [rbx], rax
0x180031978  lea     r8, [rdi+0B8h]
0x18003197f  cmp     qword ptr [r8+18h], 0Fh
0x180031984  jbe     short loc_180031989
0x180031986  mov     r8, [r8]; Source
0x180031989  mov     rdx, [rdi+0C8h]
0x180031990  inc     rdx; SizeInBytes
0x180031993  mov     rcx, rax; Destination
0x180031996  call    cs:__imp_strcpy_s
0x18003199c  xor     eax, eax
0x18003199e  mov     rbx, [rsp+38h+arg_0]
0x1800319a3  add     rsp, 30h
0x1800319a7  pop     rdi
0x1800319a8  retn
```
