# CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::FreePatterns(WICBitmapPattern *,uint,uint)

- ea: `0x1800d2484`
- end: `0x1800d2504`
- name: `?FreePatterns@?$CPatternMarshaler@UWICBitmapPattern@@VCCodecInfoCallPolicy@@@@CAXPEAUWICBitmapPattern@@II@Z`
- size: `128`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d212c`
- `0x1800d228c`
- `0x1800da788`
- `0x1800da8e8`

## callees

- `0x1800d2484`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d24b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d24d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d24ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d24b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d24d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d24ec`

## pseudocode

```c
void __fastcall CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::FreePatterns(
        char *pv,
        unsigned int a2,
        unsigned int a3)
{
  __int64 v5; // rdi
  __int64 v6; // r14
  char *v7; // rcx
  char *v8; // rcx

  if ( pv )
  {
    if ( a2 )
    {
      v5 = 0;
      v6 = a3;
      do
      {
        v7 = *(char **)&pv[40 * v5 + 16];
        if ( v7 < pv || v7 >= &pv[v6] )
          CoTaskMemFree(v7);
        v8 = *(char **)&pv[40 * v5 + 24];
        if ( v8 < pv || v8 >= &pv[v6] )
          CoTaskMemFree(v8);
        v5 = (unsigned int)(v5 + 1);
      }
      while ( (unsigned int)v5 < a2 );
    }
    CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x1800d2484  test    rcx, rcx
0x1800d2487  jz      short locret_1800D2502
0x1800d2489  push    rbx
0x1800d248a  push    rbp
0x1800d248b  push    rsi
0x1800d248c  push    rdi
0x1800d248d  push    r14
0x1800d248f  sub     rsp, 20h
0x1800d2493  mov     esi, edx
0x1800d2495  mov     rbx, rcx
0x1800d2498  test    edx, edx
0x1800d249a  jz      short loc_1800D24E9
0x1800d249c  xor     edi, edi
0x1800d249e  mov     r14d, r8d
0x1800d24a1  lea     rbp, [rdi+rdi*4]
0x1800d24a5  mov     rcx, [rbx+rbp*8+10h]; pv
0x1800d24aa  cmp     rcx, rbx
0x1800d24ad  jb      short loc_1800D24B8
0x1800d24af  lea     rax, [r14+rbx]
0x1800d24b3  cmp     rcx, rax
0x1800d24b6  jb      short loc_1800D24C4
0x1800d24b8  call    cs:__imp_CoTaskMemFree
0x1800d24bf  nop     dword ptr [rax+rax+00h]
0x1800d24c4  mov     rcx, [rbx+rbp*8+18h]; pv
0x1800d24c9  cmp     rcx, rbx
0x1800d24cc  jb      short loc_1800D24D7
0x1800d24ce  lea     rax, [r14+rbx]
0x1800d24d2  cmp     rcx, rax
0x1800d24d5  jb      short loc_1800D24E3
0x1800d24d7  call    cs:__imp_CoTaskMemFree
0x1800d24de  nop     dword ptr [rax+rax+00h]
0x1800d24e3  inc     edi
0x1800d24e5  cmp     edi, esi
0x1800d24e7  jb      short loc_1800D24A1
0x1800d24e9  mov     rcx, rbx; pv
0x1800d24ec  call    cs:__imp_CoTaskMemFree
0x1800d24f3  nop     dword ptr [rax+rax+00h]
0x1800d24f8  add     rsp, 20h
0x1800d24fc  pop     r14
0x1800d24fe  pop     rdi
0x1800d24ff  pop     rsi
0x1800d2500  pop     rbp
0x1800d2501  pop     rbx
0x1800d2502  retn
```
