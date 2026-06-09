# ShareClass::CPC_Init(void)

- ea: `0x18018fb40`
- end: `0x18018fc08`
- name: `?CPC_Init@ShareClass@@AEAAXXZ`
- size: `200`
- prototype: `void __fastcall(ShareClass *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18007381c`

## callees

- `0x18007f42c`

## import_xrefs

- `RDPBASE!CAPAPI_InitializeCombinedCaps` at `0x18018fbc0`
- `RDPBASE!CAPAPI_InitializeCombinedCaps` at `0x18018fbce`
- `RDPBASE!CAPAPI_InitializeCombinedCaps` at `0x18018fbdc`
- `RDPBASE!CAPAPI_InitializeCombinedCaps` at `0x18018fbea`
- `RDPBASE!CAPAPI_InitializeCombinedCaps` at `0x18018fbc0`
- `RDPBASE!CAPAPI_InitializeCombinedCaps` at `0x18018fbce`
- `RDPBASE!CAPAPI_InitializeCombinedCaps` at `0x18018fbdc`
- `RDPBASE!CAPAPI_InitializeCombinedCaps` at `0x18018fbea`

## pseudocode

```c
void __fastcall ShareClass::CPC_Init(ShareClass *this)
{
  __int64 v2; // r9
  __int64 v3; // r9
  __int64 v4; // r9
  __int64 v5; // r9

  *((_BYTE *)this + 72) = 0;
  memset_0((char *)this + 76, 0, 0x3E4u);
  memset_0((char *)this + 1072, 0, 0x3E4u);
  memset_0((char *)this + 2068, 0, 0x3E4u);
  *((_DWORD *)this + 766) = 0;
  memset_0((char *)this + 3068, 0, 0x3E4u);
  *((_BYTE *)this + 4064) = 0;
  CAPAPI_InitializeCombinedCaps((char *)this + 76, 0, 0, v2);
  CAPAPI_InitializeCombinedCaps((char *)this + 1072, 0, 0, v3);
  CAPAPI_InitializeCombinedCaps((char *)this + 2068, 0, 0, v4);
  CAPAPI_InitializeCombinedCaps((char *)this + 3068, 0, 0, v5);
  *((_DWORD *)this + 766) = 0;
}

```

## disassembly

```asm
0x18018fb40  push    rbx
0x18018fb42  push    rbp
0x18018fb43  push    rsi
0x18018fb44  push    rdi
0x18018fb45  push    r14
0x18018fb47  push    r15
0x18018fb49  sub     rsp, 28h
0x18018fb4d  mov     r14, rcx
0x18018fb50  mov     byte ptr [rcx+48h], 0
0x18018fb54  mov     r15d, 3E4h
0x18018fb5a  xor     edx, edx; Val
0x18018fb5c  mov     r8d, r15d; Size
0x18018fb5f  add     rcx, 4Ch ; 'L'; void *
0x18018fb63  call    memset_0
0x18018fb68  lea     rsi, [r14+430h]
0x18018fb6f  mov     r8d, r15d; Size
0x18018fb72  mov     rcx, rsi; void *
0x18018fb75  xor     edx, edx; Val
0x18018fb77  call    memset_0
0x18018fb7c  lea     rdi, [r14+814h]
0x18018fb83  mov     r8d, r15d; Size
0x18018fb86  mov     rcx, rdi; void *
0x18018fb89  xor     edx, edx; Val
0x18018fb8b  call    memset_0
0x18018fb90  lea     rbx, [r14+0BFCh]
0x18018fb97  mov     dword ptr [r14+0BF8h], 0
0x18018fba2  mov     rcx, rbx; void *
0x18018fba5  mov     r8d, r15d; Size
0x18018fba8  xor     edx, edx; Val
0x18018fbaa  call    memset_0
0x18018fbaf  xor     r8d, r8d
0x18018fbb2  mov     byte ptr [r14+0FE0h], 0
0x18018fbba  xor     edx, edx
0x18018fbbc  lea     rcx, [r14+4Ch]
0x18018fbc0  call    cs:__imp_CAPAPI_InitializeCombinedCaps
0x18018fbc6  xor     r8d, r8d
0x18018fbc9  xor     edx, edx
0x18018fbcb  mov     rcx, rsi
0x18018fbce  call    cs:__imp_CAPAPI_InitializeCombinedCaps
0x18018fbd4  xor     r8d, r8d
0x18018fbd7  xor     edx, edx
0x18018fbd9  mov     rcx, rdi
0x18018fbdc  call    cs:__imp_CAPAPI_InitializeCombinedCaps
0x18018fbe2  xor     r8d, r8d
0x18018fbe5  xor     edx, edx
0x18018fbe7  mov     rcx, rbx
0x18018fbea  call    cs:__imp_CAPAPI_InitializeCombinedCaps
0x18018fbf0  mov     dword ptr [r14+0BF8h], 0
0x18018fbfb  add     rsp, 28h
0x18018fbff  pop     r15
0x18018fc01  pop     r14
0x18018fc03  pop     rdi
0x18018fc04  pop     rsi
0x18018fc05  pop     rbp
0x18018fc06  pop     rbx
0x18018fc07  retn
```
