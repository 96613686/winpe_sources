# CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::FreePatterns(WICBitmapPattern *,uint,uint)

- ea: `0x1800cfbd8`
- end: `0x1800cfc45`
- name: `?FreePatterns@?$CPatternMarshaler@UWICBitmapPattern@@VCCodecInfoCallPolicy@@@@CAXPEAUWICBitmapPattern@@II@Z`
- size: `109`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800cf898`
- `0x1800cf9e8`
- `0x1800d7c4c`
- `0x1800d7d9c`

## callees

- `0x1800cfbd8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cfc0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cfc25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cfc34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cfc0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cfc25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cfc34`

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
0x1800cfbd8  test    rcx, rcx
0x1800cfbdb  jz      short locret_1800CFC44
0x1800cfbdd  push    rbx
0x1800cfbde  push    rbp
0x1800cfbdf  push    rsi
0x1800cfbe0  push    rdi
0x1800cfbe1  push    r14
0x1800cfbe3  sub     rsp, 20h
0x1800cfbe7  mov     esi, edx
0x1800cfbe9  mov     rbx, rcx
0x1800cfbec  test    edx, edx
0x1800cfbee  jz      short loc_1800CFC31
0x1800cfbf0  xor     edi, edi
0x1800cfbf2  mov     r14d, r8d
0x1800cfbf5  lea     rbp, [rdi+rdi*4]
0x1800cfbf9  mov     rcx, [rbx+rbp*8+10h]; pv
0x1800cfbfe  cmp     rcx, rbx
0x1800cfc01  jb      short loc_1800CFC0C
0x1800cfc03  lea     rax, [r14+rbx]
0x1800cfc07  cmp     rcx, rax
0x1800cfc0a  jb      short loc_1800CFC12
0x1800cfc0c  call    cs:__imp_CoTaskMemFree
0x1800cfc12  mov     rcx, [rbx+rbp*8+18h]; pv
0x1800cfc17  cmp     rcx, rbx
0x1800cfc1a  jb      short loc_1800CFC25
0x1800cfc1c  lea     rax, [r14+rbx]
0x1800cfc20  cmp     rcx, rax
0x1800cfc23  jb      short loc_1800CFC2B
0x1800cfc25  call    cs:__imp_CoTaskMemFree
0x1800cfc2b  inc     edi
0x1800cfc2d  cmp     edi, esi
0x1800cfc2f  jb      short loc_1800CFBF5
0x1800cfc31  mov     rcx, rbx; pv
0x1800cfc34  call    cs:__imp_CoTaskMemFree
0x1800cfc3a  add     rsp, 20h
0x1800cfc3e  pop     r14
0x1800cfc40  pop     rdi
0x1800cfc41  pop     rsi
0x1800cfc42  pop     rbp
0x1800cfc43  pop     rbx
0x1800cfc44  retn
```
