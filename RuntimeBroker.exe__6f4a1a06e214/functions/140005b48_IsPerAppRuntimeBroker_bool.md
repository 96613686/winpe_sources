# IsPerAppRuntimeBroker(bool *)

- ea: `0x140005b48`
- end: `0x140005beb`
- name: `?IsPerAppRuntimeBroker@@YAJPEA_N@Z`
- size: `163`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005770`

## callees

- `0x140005b48`
- `0x140008c80`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x140005baf`
- `ntdll!RtlNtStatusToDosError` at `0x140005baf`
- `ntdll!RtlQueryPackageIdentity` at `0x140005b94`
- `ntdll!RtlQueryPackageIdentity` at `0x140005b94`

## pseudocode

```c
signed int __fastcall IsPerAppRuntimeBroker(bool *a1)
{
  NTSTATUS v1; // ecx
  signed int result; // eax
  __int64 v3; // [rsp+30h] [rbp-128h] BYREF
  _BYTE v4[256]; // [rsp+40h] [rbp-118h] BYREF

  byte_140018608 = 0;
  v3 = 256;
  v1 = RtlQueryPackageIdentity(-4, v4, &v3);
  if ( (int)(v1 + 0x80000000) < 0 || v1 == -1073741275 )
  {
    byte_140018608 = v1 >= 0;
    return 0;
  }
  else
  {
    result = RtlNtStatusToDosError(v1);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x140005b48  sub     rsp, 158h
0x140005b4f  mov     rax, cs:__security_cookie
0x140005b56  xor     rax, rsp
0x140005b59  mov     [rsp+158h+var_18], rax
0x140005b61  xor     r9d, r9d
0x140005b64  mov     [rsp+158h+var_130], 0
0x140005b6d  lea     r8, [rsp+158h+var_128]
0x140005b72  mov     cs:byte_140018608, 0
0x140005b79  lea     rdx, [rsp+158h+var_118]
0x140005b7e  mov     [rsp+158h+var_128], 100h
0x140005b87  mov     [rsp+158h+var_138], 0
0x140005b90  lea     rcx, [r9-4]
0x140005b94  call    cs:__imp_RtlQueryPackageIdentity
0x140005b9a  mov     edx, 80000000h
0x140005b9f  mov     ecx, eax; Status
0x140005ba1  add     eax, edx
0x140005ba3  test    edx, eax
0x140005ba5  jnz     short loc_140005BD1
0x140005ba7  cmp     ecx, 0C0000225h
0x140005bad  jz      short loc_140005BD1
0x140005baf  call    cs:__imp_RtlNtStatusToDosError
0x140005bb5  test    eax, eax
0x140005bb7  jg      short loc_140005BE1
0x140005bb9  mov     rcx, [rsp+158h+var_18]
0x140005bc1  xor     rcx, rsp; StackCookie
0x140005bc4  call    __security_check_cookie
0x140005bc9  add     rsp, 158h
0x140005bd0  retn
0x140005bd1  shr     ecx, 1Fh
0x140005bd4  xor     cl, 1
0x140005bd7  mov     cs:byte_140018608, cl
0x140005bdd  xor     eax, eax
0x140005bdf  jmp     short loc_140005BB9
0x140005be1  movzx   eax, ax
0x140005be4  or      eax, 80070000h
0x140005be9  jmp     short loc_140005BB9
```
