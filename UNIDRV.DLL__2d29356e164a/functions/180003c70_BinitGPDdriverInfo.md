# BinitGPDdriverInfo

- ea: `0x180003c70`
- end: `0x180003d87`
- name: `BinitGPDdriverInfo`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005620`

## callees

- `0x180003c70`
- `0x180004b70`
- `0x180005000`
- `0x180007220`

## string_xrefs

- `0x180003d67`: `BinitGPDdriverInfo: Unable to init sequence commands`

## pseudocode

```c
__int64 __fastcall BinitGPDdriverInfo(__int64 a1, __int64 a2, __int64 a3)
{
  *(_DWORD *)a1 = 480;
  *(_QWORD *)(a1 + 96) = *(_QWORD *)(a2 + 72) + **(unsigned int **)(a2 + 96);
  *(_DWORD *)(a1 + 16) = *(_DWORD *)(*(_QWORD *)(a2 + 96) + 48LL) - **(_DWORD **)(a2 + 96);
  *(_DWORD *)(a1 + 12) = *(_DWORD *)(*(_QWORD *)(a2 + 96) + 52LL);
  *(_DWORD *)(a1 + 24) = *(_DWORD *)(*(_QWORD *)(a2 + 96) + 60LL) - **(_DWORD **)(a2 + 96);
  *(_DWORD *)(a1 + 20) = *(_DWORD *)(*(_QWORD *)(a2 + 96) + 64LL);
  *(_DWORD *)(a1 + 32) = *(_DWORD *)(*(_QWORD *)(a2 + 96) + 72LL) - **(_DWORD **)(a2 + 96);
  *(_DWORD *)(a1 + 28) = *(_DWORD *)(*(_QWORD *)(a2 + 96) + 76LL);
  *(_DWORD *)(a1 + 40) = *(_DWORD *)(*(_QWORD *)(a2 + 96) + 84LL) - **(_DWORD **)(a2 + 96);
  *(_DWORD *)(a1 + 36) = *(_DWORD *)(*(_QWORD *)(a2 + 96) + 88LL);
  *(_DWORD *)(a1 + 56) = *(_DWORD *)(*(_QWORD *)(a2 + 96) + 180LL) - **(_DWORD **)(a2 + 96);
  *(_DWORD *)(a1 + 52) = *(_DWORD *)(*(_QWORD *)(a2 + 96) + 184LL);
  *(_DWORD *)(a1 + 64) = *(_DWORD *)(*(_QWORD *)(a2 + 96) + 168LL) - **(_DWORD **)(a2 + 96);
  *(_DWORD *)(a1 + 60) = *(_DWORD *)(*(_QWORD *)(a2 + 96) + 172LL);
  if ( (unsigned int)BinitSequencedCmds(a1, a2) )
  {
    if ( (unsigned int)BinitGlobals(a1 + 112, a2, a3) )
      return 1;
    WriteDbgTraceErrorGpd(
      (__int64)"BinitGPDdriverInfo",
      "BinitGPDdriverInfo: unexpected failure initilizing PGLOBAL data");
  }
  else
  {
    WriteDbgTraceErrorGpd((__int64)"BinitGPDdriverInfo", "BinitGPDdriverInfo: Unable to init sequence commands");
  }
  return 0;
}

```

## disassembly

```asm
0x180003c70  mov     [rsp+arg_0], rbx
0x180003c75  mov     [rsp+arg_8], rsi
0x180003c7a  push    rdi
0x180003c7b  sub     rsp, 20h
0x180003c7f  mov     dword ptr [rcx], 1E0h
0x180003c85  mov     rdi, rcx
0x180003c88  mov     rax, [rdx+60h]
0x180003c8c  mov     rbx, rdx
0x180003c8f  mov     rsi, r8
0x180003c92  mov     r9d, [rax]
0x180003c95  add     r9, [rdx+48h]
0x180003c99  mov     [rcx+60h], r9
0x180003c9d  mov     rax, [rdx+60h]
0x180003ca1  mov     r9d, [rax+30h]
0x180003ca5  sub     r9d, [rax]
0x180003ca8  mov     [rcx+10h], r9d
0x180003cac  mov     rax, [rdx+60h]
0x180003cb0  mov     edx, [rax+34h]
0x180003cb3  mov     [rcx+0Ch], edx
0x180003cb6  mov     rdx, rbx
0x180003cb9  mov     rax, [rbx+60h]
0x180003cbd  mov     ecx, [rax+3Ch]
0x180003cc0  sub     ecx, [rax]
0x180003cc2  mov     [rdi+18h], ecx
0x180003cc5  mov     rax, [rbx+60h]
0x180003cc9  mov     ecx, [rax+40h]
0x180003ccc  mov     [rdi+14h], ecx
0x180003ccf  mov     rax, [rbx+60h]
0x180003cd3  mov     ecx, [rax+48h]
0x180003cd6  sub     ecx, [rax]
0x180003cd8  mov     [rdi+20h], ecx
0x180003cdb  mov     rax, [rbx+60h]
0x180003cdf  mov     ecx, [rax+4Ch]
0x180003ce2  mov     [rdi+1Ch], ecx
0x180003ce5  mov     rax, [rbx+60h]
0x180003ce9  mov     ecx, [rax+54h]
0x180003cec  sub     ecx, [rax]
0x180003cee  mov     [rdi+28h], ecx
0x180003cf1  mov     rax, [rbx+60h]
0x180003cf5  mov     ecx, [rax+58h]
0x180003cf8  mov     [rdi+24h], ecx
0x180003cfb  mov     rax, [rbx+60h]
0x180003cff  mov     ecx, [rax+0B4h]
0x180003d05  sub     ecx, [rax]
0x180003d07  mov     [rdi+38h], ecx
0x180003d0a  mov     rax, [rbx+60h]
0x180003d0e  mov     ecx, [rax+0B8h]
0x180003d14  mov     [rdi+34h], ecx
0x180003d17  mov     rax, [rbx+60h]
0x180003d1b  mov     ecx, [rax+0A8h]
0x180003d21  sub     ecx, [rax]
0x180003d23  mov     [rdi+40h], ecx
0x180003d26  mov     rax, [rbx+60h]
0x180003d2a  mov     ecx, [rax+0ACh]
0x180003d30  mov     [rdi+3Ch], ecx
0x180003d33  mov     rcx, rdi
0x180003d36  call    BinitSequencedCmds
0x180003d3b  test    eax, eax
0x180003d3d  jz      short loc_180003D67
0x180003d3f  lea     rcx, [rdi+70h]
0x180003d43  mov     r8, rsi
0x180003d46  mov     rdx, rbx
0x180003d49  call    BinitGlobals
0x180003d4e  test    eax, eax
0x180003d50  jz      short loc_180003D7E
0x180003d52  mov     eax, 1
0x180003d57  mov     rbx, [rsp+28h+arg_0]
0x180003d5c  mov     rsi, [rsp+28h+arg_8]
0x180003d61  add     rsp, 20h
0x180003d65  pop     rdi
0x180003d66  retn
0x180003d67  lea     rdx, aBinitgpddriver; "BinitGPDdriverInfo: Unable to init sequ"...
0x180003d6e  lea     rcx, aBinitgpddriver_1; "BinitGPDdriverInfo"
0x180003d75  call    WriteDbgTraceErrorGpd
0x180003d7a  xor     eax, eax
0x180003d7c  jmp     short loc_180003D57
0x180003d7e  lea     rdx, aBinitgpddriver_0; "BinitGPDdriverInfo: unexpected failure "...
0x180003d85  jmp     short loc_180003D6E
```
