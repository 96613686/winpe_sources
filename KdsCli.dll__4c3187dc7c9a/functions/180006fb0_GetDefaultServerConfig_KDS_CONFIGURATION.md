# GetDefaultServerConfig(_KDS_CONFIGURATION * *)

- ea: `0x180006fb0`
- end: `0x180007053`
- name: `?GetDefaultServerConfig@@YAJPEAPEAU_KDS_CONFIGURATION@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(struct _KDS_CONFIGURATION **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007060`

## callees

- `0x180006fb0`
- `0x180010920`
- `0x18001a450`

## string_xrefs

- `0x180006fd2`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdssrvconfig.cxx`

## pseudocode

```c
__int64 __fastcall GetDefaultServerConfig(struct _KDS_CONFIGURATION **a1)
{
  _DWORD *v2; // rax
  unsigned int v3; // ebx

  v2 = SIDKeyProvAlloc(0x58u);
  if ( v2 )
  {
    v2[6] = 30;
    *((_QWORD *)v2 + 1) = L"SP800_108_CTR_HMAC";
    v3 = 0;
    v2[13] = 512;
    *((_QWORD *)v2 + 2) = qword_18001D660;
    *((_QWORD *)v2 + 4) = L"DH";
    *((_QWORD *)v2 + 5) = qword_18001D680;
    *v2 = 1;
    v2[14] = 2048;
    v2[12] = 524;
    v2[18] = 1;
    *a1 = (struct _KDS_CONFIGURATION *)v2;
  }
  else
  {
    v3 = -2147024882;
    SidKeyDebugTraceError(
      0x8007000E,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdssrvconfig.cxx",
      0x26Fu);
  }
  return v3;
}

```

## disassembly

```asm
0x180006fb0  mov     [rsp+arg_0], rbx
0x180006fb5  push    rdi
0x180006fb6  sub     rsp, 20h
0x180006fba  mov     rdi, rcx
0x180006fbd  mov     ecx, 58h ; 'X'; unsigned __int64
0x180006fc2  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180006fc7  test    rax, rax
0x180006fca  jnz     short loc_180006FF1
0x180006fcc  mov     r9d, 26Fh; unsigned int
0x180006fd2  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180006fd9  lea     rdx, aHr; "hr"
0x180006fe0  mov     ecx, 8007000Eh; unsigned int
0x180006fe5  mov     ebx, 8007000Eh
0x180006fea  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180006fef  jmp     short loc_180007046
0x180006ff1  lea     rcx, aSp800108CtrHma; "SP800_108_CTR_HMAC"
0x180006ff8  mov     dword ptr [rax+18h], 1Eh
0x180006fff  mov     [rax+8], rcx
0x180007003  xor     ebx, ebx
0x180007005  lea     rcx, qword_18001D660
0x18000700c  mov     dword ptr [rax+34h], 200h
0x180007013  mov     [rax+10h], rcx
0x180007017  lea     rcx, aDh; "DH"
0x18000701e  mov     [rax+20h], rcx
0x180007022  lea     rcx, qword_18001D680
0x180007029  lea     edx, [rbx+1]
0x18000702c  mov     [rax+28h], rcx
0x180007030  mov     [rax], edx
0x180007032  mov     dword ptr [rax+38h], 800h
0x180007039  mov     dword ptr [rax+30h], 20Ch
0x180007040  mov     [rax+48h], edx
0x180007043  mov     [rdi], rax
0x180007046  mov     eax, ebx
0x180007048  mov     rbx, [rsp+28h+arg_0]
0x18000704d  add     rsp, 20h
0x180007051  pop     rdi
0x180007052  retn
```
