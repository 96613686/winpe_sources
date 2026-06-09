# BinitGPDdriverInfo

- ea: `0x180003c88`
- end: `0x180003da0`
- name: `BinitGPDdriverInfo`
- size: `280`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005544`

## callees

- `0x180003c88`
- `0x180004a90`
- `0x180004f20`
- `0x180007150`

## string_xrefs

- `0x180003d80`: `BinitGPDdriverInfo: Unable to init sequence commands`

## pseudocode

```c
__int64 __fastcall BinitGPDdriverInfo(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // r9d

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
  if ( (unsigned int)BinitSequencedCmds(a1, a2, a3) )
  {
    if ( (unsigned int)BinitGlobals(a1 + 112, (_QWORD *)a2, a3, v6) )
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
0x180003c88  mov     [rsp+arg_0], rbx
0x180003c8d  mov     [rsp+arg_8], rsi
0x180003c92  push    rdi
0x180003c93  sub     rsp, 20h
0x180003c97  mov     dword ptr [rcx], 1E0h
0x180003c9d  mov     rdi, rcx
0x180003ca0  mov     rax, [rdx+60h]
0x180003ca4  mov     rbx, rdx
0x180003ca7  mov     rsi, r8
0x180003caa  mov     r9d, [rax]
0x180003cad  add     r9, [rdx+48h]
0x180003cb1  mov     [rcx+60h], r9
0x180003cb5  mov     rax, [rdx+60h]
0x180003cb9  mov     r9d, [rax+30h]
0x180003cbd  sub     r9d, [rax]
0x180003cc0  mov     [rcx+10h], r9d
0x180003cc4  mov     rax, [rdx+60h]
0x180003cc8  mov     edx, [rax+34h]
0x180003ccb  mov     [rcx+0Ch], edx
0x180003cce  mov     rdx, rbx
0x180003cd1  mov     rax, [rbx+60h]
0x180003cd5  mov     ecx, [rax+3Ch]
0x180003cd8  sub     ecx, [rax]
0x180003cda  mov     [rdi+18h], ecx
0x180003cdd  mov     rax, [rbx+60h]
0x180003ce1  mov     ecx, [rax+40h]
0x180003ce4  mov     [rdi+14h], ecx
0x180003ce7  mov     rax, [rbx+60h]
0x180003ceb  mov     ecx, [rax+48h]
0x180003cee  sub     ecx, [rax]
0x180003cf0  mov     [rdi+20h], ecx
0x180003cf3  mov     rax, [rbx+60h]
0x180003cf7  mov     ecx, [rax+4Ch]
0x180003cfa  mov     [rdi+1Ch], ecx
0x180003cfd  mov     rax, [rbx+60h]
0x180003d01  mov     ecx, [rax+54h]
0x180003d04  sub     ecx, [rax]
0x180003d06  mov     [rdi+28h], ecx
0x180003d09  mov     rax, [rbx+60h]
0x180003d0d  mov     ecx, [rax+58h]
0x180003d10  mov     [rdi+24h], ecx
0x180003d13  mov     rax, [rbx+60h]
0x180003d17  mov     ecx, [rax+0B4h]
0x180003d1d  sub     ecx, [rax]
0x180003d1f  mov     [rdi+38h], ecx
0x180003d22  mov     rax, [rbx+60h]
0x180003d26  mov     ecx, [rax+0B8h]
0x180003d2c  mov     [rdi+34h], ecx
0x180003d2f  mov     rax, [rbx+60h]
0x180003d33  mov     ecx, [rax+0A8h]
0x180003d39  sub     ecx, [rax]
0x180003d3b  mov     [rdi+40h], ecx
0x180003d3e  mov     rax, [rbx+60h]
0x180003d42  mov     ecx, [rax+0ACh]
0x180003d48  mov     [rdi+3Ch], ecx
0x180003d4b  mov     rcx, rdi
0x180003d4e  call    BinitSequencedCmds
0x180003d53  test    eax, eax
0x180003d55  jz      short loc_180003D80
0x180003d57  lea     rcx, [rdi+70h]
0x180003d5b  mov     r8, rsi
0x180003d5e  mov     rdx, rbx
0x180003d61  call    BinitGlobals
0x180003d66  test    eax, eax
0x180003d68  jz      short loc_180003D97
0x180003d6a  mov     eax, 1
0x180003d6f  mov     rbx, [rsp+28h+arg_0]
0x180003d74  mov     rsi, [rsp+28h+arg_8]
0x180003d79  add     rsp, 20h
0x180003d7d  pop     rdi
0x180003d7e  retn
0x180003d80  lea     rdx, aBinitgpddriver; "BinitGPDdriverInfo: Unable to init sequ"...
0x180003d87  lea     rcx, aBinitgpddriver_1; "BinitGPDdriverInfo"
0x180003d8e  call    WriteDbgTraceErrorGpd
0x180003d93  xor     eax, eax
0x180003d95  jmp     short loc_180003D6F
0x180003d97  lea     rdx, aBinitgpddriver_0; "BinitGPDdriverInfo: unexpected failure "...
0x180003d9e  jmp     short loc_180003D87
```
