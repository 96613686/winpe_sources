# Broker::BackgroundAccessApplicationsWrapper::FreeBackgroundAccessAppList(ushort * *,ushort * *,uint)

- ea: `0x18000c320`
- end: `0x18000c39e`
- name: `?FreeBackgroundAccessAppList@BackgroundAccessApplicationsWrapper@Broker@@CAXPEAPEAG0I@Z`
- size: `126`
- prototype: `void __fastcall(unsigned __int16 **pv, unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c2c0`

## callees

- `0x18000c320`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c366`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c375`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c387`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c396`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c366`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c375`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c387`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c396`

## pseudocode

```c
void __fastcall Broker::BackgroundAccessApplicationsWrapper::FreeBackgroundAccessAppList(
        unsigned __int16 **pv,
        unsigned __int16 **a2,
        unsigned int a3)
{
  __int64 i; // rbx
  __int64 j; // rbx

  if ( pv )
  {
    for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
      CoTaskMemFree(pv[i]);
    CoTaskMemFree(pv);
  }
  if ( a2 )
  {
    for ( j = 0; (unsigned int)j < a3; j = (unsigned int)(j + 1) )
      CoTaskMemFree(a2[j]);
    CoTaskMemFree(a2);
  }
}

```

## disassembly

```asm
0x18000c320  mov     [rsp+arg_8], rbx
0x18000c325  mov     [rsp+arg_10], rsi
0x18000c32a  push    rdi
0x18000c32b  sub     rsp, 20h
0x18000c32f  mov     [rsp+28h+arg_0], r14
0x18000c334  mov     r14, rcx
0x18000c337  mov     edi, r8d
0x18000c33a  mov     rsi, rdx
0x18000c33d  test    rcx, rcx
0x18000c340  jnz     short loc_18000C35C
0x18000c342  mov     r14, [rsp+28h+arg_0]
0x18000c347  test    rsi, rsi
0x18000c34a  jnz     short loc_18000C37D
0x18000c34c  mov     rbx, [rsp+28h+arg_8]
0x18000c351  mov     rsi, [rsp+28h+arg_10]
0x18000c356  add     rsp, 20h
0x18000c35a  pop     rdi
0x18000c35b  retn
0x18000c35c  xor     ebx, ebx
0x18000c35e  test    edi, edi
0x18000c360  jz      short loc_18000C372
0x18000c362  mov     rcx, [r14+rbx*8]; pv
0x18000c366  call    cs:__imp_CoTaskMemFree
0x18000c36c  inc     ebx
0x18000c36e  cmp     ebx, edi
0x18000c370  jb      short loc_18000C362
0x18000c372  mov     rcx, r14; pv
0x18000c375  call    cs:__imp_CoTaskMemFree
0x18000c37b  jmp     short loc_18000C342
0x18000c37d  xor     ebx, ebx
0x18000c37f  test    edi, edi
0x18000c381  jz      short loc_18000C393
0x18000c383  mov     rcx, [rsi+rbx*8]; pv
0x18000c387  call    cs:__imp_CoTaskMemFree
0x18000c38d  inc     ebx
0x18000c38f  cmp     ebx, edi
0x18000c391  jb      short loc_18000C383
0x18000c393  mov     rcx, rsi; pv
0x18000c396  call    cs:__imp_CoTaskMemFree
0x18000c39c  jmp     short loc_18000C34C
```
