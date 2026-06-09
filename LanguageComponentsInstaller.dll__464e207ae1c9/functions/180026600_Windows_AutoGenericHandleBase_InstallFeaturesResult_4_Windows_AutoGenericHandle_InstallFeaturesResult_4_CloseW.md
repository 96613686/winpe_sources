# Windows::AutoGenericHandleBase<InstallFeaturesResult,4,Windows::AutoGenericHandle<InstallFeaturesResult,4,&CloseWithFreeInstallFeaturesResult(InstallFeaturesResult)>>::~AutoGenericHandleBase<InstallFeaturesResult,4,Windows::AutoGenericHandle<InstallFeaturesResult,4,&CloseWithFreeInstallFeaturesResult(InstallFeaturesResult)>>(void)

- ea: `0x180026600`
- end: `0x1800266a1`
- name: `??1?$AutoGenericHandleBase@UInstallFeaturesResult@@$03V?$AutoGenericHandle@UInstallFeaturesResult@@$03$1?CloseWithFreeInstallFeaturesResult@@YAXU1@@Z@Windows@@@Windows@@QEAA@XZ`
- size: `161`
- prototype: `int __fastcall(__int128 *Buf1)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800269c0`

## callees

- `0x1800040f4`
- `0x180004118`
- `0x180026600`

## import_xrefs

- `ServicingUAPI!FreeInstallFeaturesResult` at `0x18002665e`
- `ServicingUAPI!FreeInstallFeaturesResult` at `0x18002665e`

## pseudocode

```c
int __fastcall Windows::AutoGenericHandleBase<InstallFeaturesResult,4,Windows::AutoGenericHandle<InstallFeaturesResult,4,&void CloseWithFreeInstallFeaturesResult(InstallFeaturesResult)>>::~AutoGenericHandleBase<InstallFeaturesResult,4,Windows::AutoGenericHandle<InstallFeaturesResult,4,&void CloseWithFreeInstallFeaturesResult(InstallFeaturesResult)>>(
        __int128 *Buf1)
{
  int result; // eax
  __int128 v3; // xmm1
  __int128 v4; // xmm0
  __int128 v5; // xmm1
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 Buf2; // [rsp+20h] [rbp-40h] BYREF
  __int128 v10; // [rsp+30h] [rbp-30h]
  __int128 v11; // [rsp+40h] [rbp-20h]
  __int128 v12; // [rsp+50h] [rbp-10h]

  memset_0(&Buf2, 0, 0x40u);
  result = memcmp_0(Buf1, &Buf2, 0x40u);
  if ( result )
  {
    v3 = Buf1[1];
    Buf2 = *Buf1;
    v4 = Buf1[2];
    v10 = v3;
    v5 = Buf1[3];
    v11 = v4;
    v12 = v5;
    FreeInstallFeaturesResult(&Buf2);
    result = (unsigned int)memset_0(&Buf2, 0, 0x40u);
    v6 = v10;
    *Buf1 = Buf2;
    v7 = v11;
    Buf1[1] = v6;
    v8 = v12;
    Buf1[2] = v7;
    Buf1[3] = v8;
  }
  return result;
}

```

## disassembly

```asm
0x180026600  mov     [rsp-8+arg_0], rbx
0x180026605  mov     [rsp-8+arg_8], rdi
0x18002660a  push    rbp
0x18002660b  mov     rbp, rsp
0x18002660e  sub     rsp, 60h
0x180026612  mov     rbx, rcx
0x180026615  mov     edi, 40h ; '@'
0x18002661a  mov     r8d, edi; Size
0x18002661d  lea     rcx, [rbp+Buf2]; void *
0x180026621  xor     edx, edx; Val
0x180026623  call    memset_0
0x180026628  mov     r8d, edi; Size
0x18002662b  lea     rdx, [rbp+Buf2]; Buf2
0x18002662f  mov     rcx, rbx; Buf1
0x180026632  call    memcmp_0
0x180026637  test    eax, eax
0x180026639  jz      short loc_180026691
0x18002663b  movups  xmm0, xmmword ptr [rbx]
0x18002663e  lea     rcx, [rbp+Buf2]
0x180026642  movups  xmm1, xmmword ptr [rbx+10h]
0x180026646  movaps  [rbp+Buf2], xmm0
0x18002664a  movups  xmm0, xmmword ptr [rbx+20h]
0x18002664e  movaps  [rbp+var_30], xmm1
0x180026652  movups  xmm1, xmmword ptr [rbx+30h]
0x180026656  movaps  [rbp+var_20], xmm0
0x18002665a  movaps  [rbp+var_10], xmm1
0x18002665e  call    cs:__imp_FreeInstallFeaturesResult
0x180026664  mov     r8d, edi; Size
0x180026667  lea     rcx, [rbp+Buf2]; void *
0x18002666b  xor     edx, edx; Val
0x18002666d  call    memset_0
0x180026672  movups  xmm0, [rbp+Buf2]
0x180026676  movups  xmm1, [rbp+var_30]
0x18002667a  movups  xmmword ptr [rbx], xmm0
0x18002667d  movups  xmm0, [rbp+var_20]
0x180026681  movups  xmmword ptr [rbx+10h], xmm1
0x180026685  movups  xmm1, [rbp+var_10]
0x180026689  movups  xmmword ptr [rbx+20h], xmm0
0x18002668d  movups  xmmword ptr [rbx+30h], xmm1
0x180026691  mov     rbx, [rsp+60h+arg_0]
0x180026696  mov     rdi, [rsp+60h+arg_8]
0x18002669b  add     rsp, 60h
0x18002669f  pop     rbp
0x1800266a0  retn
```
