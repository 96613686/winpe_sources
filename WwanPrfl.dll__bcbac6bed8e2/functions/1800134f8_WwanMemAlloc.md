# WwanMemAlloc

- ea: `0x1800134f8`
- end: `0x18001358a`
- name: `WwanMemAlloc`
- size: `146`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x18000b880`
- `0x18000cf80`
- `0x18000db40`
- `0x18000dea0`
- `0x180010a24`
- `0x1800114a0`
- `0x180011974`

## callees

- `0x180001670`
- `0x180002034`
- `0x180002094`
- `0x180013498`
- `0x1800134f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013569`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013569`

## pseudocode

```c
void *__fastcall WwanMemAlloc(size_t Size)
{
  void *v2; // rax
  int v3; // edx
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  void *v7; // rbx
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-38h] BYREF
  const char *v10; // [rsp+40h] [rbp-28h]
  __int64 v11; // [rsp+48h] [rbp-20h]

  v2 = operator new[](Size, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v2;
  if ( v2 )
  {
    memset_0(v2, 0, Size);
  }
  else
  {
    if ( (WwanControlGuid_61954a80b9663f9147495ff35ed68ca1EnableBits & 1) != 0 )
    {
      v11 = 13;
      v10 = "WwanMemAlloc";
      McGenEventWrite_EventWriteTransfer(v4, v3, v5, v6, &v9);
    }
    SetLastError(8u);
  }
  return v7;
}

```

## disassembly

```asm
0x1800134f8  mov     [rsp+arg_8], rbx
0x1800134fd  push    rdi
0x1800134fe  sub     rsp, 60h
0x180013502  mov     rax, cs:__security_cookie
0x180013509  xor     rax, rsp
0x18001350c  mov     [rsp+68h+var_18], rax
0x180013511  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013518  mov     rdi, rcx
0x18001351b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180013520  mov     rbx, rax
0x180013523  test    rax, rax
0x180013526  jz      short loc_180013537
0x180013528  mov     r8, rdi; Size
0x18001352b  xor     edx, edx; Val
0x18001352d  mov     rcx, rax; void *
0x180013530  call    memset_0
0x180013535  jmp     short loc_18001356F
0x180013537  test    cs:WwanControlGuid_61954a80b9663f9147495ff35ed68ca1EnableBits, 1
0x18001353e  jz      short loc_180013564
0x180013540  lea     rax, aWwanmemalloc; "WwanMemAlloc"
0x180013547  mov     [rsp+68h+var_20], 0Dh
0x180013550  mov     [rsp+68h+var_28], rax
0x180013555  lea     rax, [rsp+68h+var_38]
0x18001355a  mov     [rsp+68h+var_48], rax; PEVENT_DATA_DESCRIPTOR
0x18001355f  call    McGenEventWrite_EventWriteTransfer
0x180013564  mov     ecx, 8; dwErrCode
0x180013569  call    cs:__imp_SetLastError
0x18001356f  mov     rax, rbx
0x180013572  mov     rcx, [rsp+68h+var_18]
0x180013577  xor     rcx, rsp; StackCookie
0x18001357a  call    __security_check_cookie
0x18001357f  mov     rbx, [rsp+68h+arg_8]
0x180013584  add     rsp, 60h
0x180013588  pop     rdi
0x180013589  retn
```
