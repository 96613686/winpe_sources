# Crashdump_UcxEvtGetDumpData

- ea: `0x140052940`
- end: `0x140052e6f`
- name: `Crashdump_UcxEvtGetDumpData`
- size: `1327`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140005a6c`
- `0x14003ce50`
- `0x140051a58`
- `0x140051d9c`
- `0x140052940`
- `0x140053af4`
- `0x140059970`
- `0x1400599b0`
- `0x140059a80`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140052990`
- `ntoskrnl!DbgPrintEx` at `0x140052de7`
- `ntoskrnl!DbgPrintEx` at `0x140052e42`
- `ntoskrnl!DbgPrintEx` at `0x140052990`
- `ntoskrnl!DbgPrintEx` at `0x140052de7`
- `ntoskrnl!DbgPrintEx` at `0x140052e42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052c60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052e22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052c60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052e22`
- `ntoskrnl!ExAllocatePool2` at `0x140052a54`
- `ntoskrnl!ExAllocatePool2` at `0x140052c00`
- `ntoskrnl!ExAllocatePool2` at `0x140052a54`
- `ntoskrnl!ExAllocatePool2` at `0x140052c00`

## string_xrefs

- `0x140052dc2`: `XHCIDUMP: CommonBuffer: Allocated %u pages, %u bytes. Used %u bytes\n`

## pseudocode

```c
__int64 __fastcall Crashdump_UcxEvtGetDumpData(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v7; // r13
  __int64 v8; // r14
  __int64 v9; // rdi
  __int64 v10; // r15
  __int64 Pool2; // rax
  _QWORD *v12; // rbx
  int v13; // edi
  _QWORD **v14; // rsi
  __int64 v15; // rdx
  int v16; // r8d
  __int64 v17; // rcx
  int v18; // edx
  int v19; // eax
  __int64 v20; // rax
  unsigned int j; // ebp
  _QWORD *v22; // rdx
  _QWORD *v23; // rax
  unsigned int i; // edi
  unsigned int v25; // eax
  unsigned int v26; // r15d
  __int64 v27; // r8
  int v28; // edx
  int v29; // edx
  __int64 v32; // [rsp+38h] [rbp-80h]
  __int128 v33; // [rsp+40h] [rbp-78h] BYREF
  __int128 v34; // [rsp+50h] [rbp-68h]
  int v35; // [rsp+60h] [rbp-58h]

  v35 = 0;
  v33 = 0;
  v34 = 0;
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UcxEvtGetDumpData: Begin\n");
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a2,
         off_14006C1A8);
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006C310);
  v9 = *(_QWORD *)(v8 + 88);
  v10 = *(_QWORD *)(v8 + 120);
  v32 = *(_QWORD *)(v8 + 136);
  *(_QWORD *)(a4 + 16) = Crashdump_Initialize;
  *(_QWORD *)(a4 + 56) = Crashdump_Cleanup;
  *(_QWORD *)(a4 + 24) = Crashdump_SendUrb;
  *(_QWORD *)(a4 + 48) = Crashdump_ResetDevice;
  *(_QWORD *)(a4 + 32) = Crashdump_SendUrbAsync;
  *(_QWORD *)(a4 + 40) = Crashdump_PollForCompletion;
  *(_BYTE *)(a4 + 84) = 0;
  Pool2 = ExAllocatePool2(64, 632, 1128482904);
  v12 = (_QWORD *)Pool2;
  if ( !Pool2 )
  {
    v13 = -1073741670;
    goto LABEL_36;
  }
  v14 = (_QWORD **)(Pool2 + 496);
  *(_QWORD *)(Pool2 + 504) = Pool2 + 496;
  *(_QWORD *)(Pool2 + 496) = Pool2 + 496;
  *(_QWORD *)(Pool2 + 488) = v10;
  v15 = *(_QWORD *)(v8 + 136);
  *(_QWORD *)Pool2 = v9;
  *(_OWORD *)(Pool2 + 8) = *(_OWORD *)(v8 + 736);
  *(_DWORD *)(Pool2 + 24) = (unsigned __int8)*(_DWORD *)(v9 + 84);
  v16 = *(_DWORD *)(v9 + 96);
  *(_DWORD *)(Pool2 + 28) = v16;
  if ( v16 )
  {
    *(_QWORD *)(Pool2 + 32) = *(_QWORD *)(*(_QWORD *)(v15 + 48) + 24LL);
    v17 = *(_QWORD *)(*(_QWORD *)(v15 + 48) + 16LL);
    *(_DWORD *)(Pool2 + 48) = 8 * v16;
    *(_QWORD *)(Pool2 + 40) = v17;
    *(_OWORD *)(Pool2 + 56) = *(_OWORD *)(v15 + 56);
  }
  v13 = Crashdump_EventRing_InitializeForDump(Pool2 + 72, Pool2);
  if ( v13 >= 0 )
  {
    v12[25] = v12;
    v12[26] = v12;
    v12[27] = *(_QWORD *)(*v12 + 40LL) + 32LL;
    v12[41] = v12;
    v12[42] = v12;
    v12[43] = *(_QWORD *)(*v12 + 32LL) + 24LL;
    v13 = Crashdump_CommonBufferAcquire((__int64)v12, 32, (__int64)(v12 + 44));
    if ( v13 >= 0 )
    {
      v18 = *(_DWORD *)(a4 + 80);
      if ( !v18 )
        goto LABEL_10;
      v13 = Crashdump_CommonBufferAcquire((__int64)v12, v18, (__int64)(v12 + 74));
      if ( v13 >= 0 )
      {
        *(_QWORD *)(a4 + 64) = v12[75];
        *(_QWORD *)(a4 + 72) = v12[74];
LABEL_10:
        *((_DWORD *)v12 + 131) = *(_DWORD *)(v7 + 20);
        *(_OWORD *)((char *)v12 + 532) = *(_OWORD *)(v7 + 32);
        *(_OWORD *)((char *)v12 + 548) = *(_OWORD *)(v7 + 48);
        *((_DWORD *)v12 + 141) = *(_DWORD *)(v7 + 64);
        v19 = 20;
        if ( *(_BYTE *)(120LL * (unsigned int)(*((_DWORD *)v12 + 136) - 1)
                      + *(_QWORD *)(*(_QWORD *)(v8 + 152) + 48LL)
                      + 13) != 2 )
          v19 = 30;
        *((_DWORD *)v12 + 132) = v19;
        v20 = ExAllocatePool2(64, 376LL * *((unsigned int *)v12 + 134), 1128482904);
        v12[71] = v20;
        if ( v20 )
        {
          for ( i = 0; ; i = v26 )
          {
            v25 = *((_DWORD *)v12 + 134);
            if ( i >= v25 )
              break;
            v26 = i + 1;
            v33 = 0;
            v35 = 0;
            v34 = 0;
            DWORD1(v33) = i + 1;
            memmove((char *)&v33 + 12, v12 + 68, 4LL * (i + 1));
            v27 = a3;
            if ( i + 1 != *((_DWORD *)v12 + 134) )
              v27 = 0;
            v13 = Crashdump_InitializeDeviceContext(v32, (int)v12, v27, (__int64)&v33, v12[71] + 376LL * i);
            if ( v13 < 0 )
              goto LABEL_14;
          }
          v12[72] = v12[71] + 376LL * (v25 - 1);
          v13 = Crashdump_CommonBufferAcquire((__int64)v12, 64, (__int64)(v12 + 55));
          if ( v13 >= 0 )
          {
            v28 = 2112;
            if ( (*(_DWORD *)(*v12 + 104LL) & 4) == 0 )
              v28 = 1056;
            v13 = Crashdump_CommonBufferAcquire((__int64)v12, v28, (__int64)(v12 + 58));
            if ( v13 >= 0 )
            {
              v29 = *((_DWORD *)v12 + 134);
              *((_DWORD *)v12 + 102) = v29;
              v13 = Crashdump_CommonBufferAcquire((__int64)v12, 8 * v29 + 8, (__int64)(v12 + 52));
              if ( v13 >= 0 )
              {
                DbgPrintEx(
                  0x93u,
                  3u,
                  "XHCIDUMP: CommonBuffer: Allocated %u pages, %u bytes. Used %u bytes\n",
                  *((_DWORD *)v12 + 128),
                  *((_DWORD *)v12 + 128) << 12,
                  *((_DWORD *)v12 + 129));
                *((_DWORD *)v12 + 146) = 0;
                v13 = 0;
                *(_QWORD *)(a4 + 8) = v12;
                v12[77] = v8;
                *(_QWORD *)(v8 + 824) = v12;
                goto LABEL_36;
              }
            }
          }
        }
        else
        {
          v13 = -1073741670;
        }
      }
    }
  }
LABEL_14:
  if ( v12[71] )
  {
    for ( j = 0; j < *((_DWORD *)v12 + 134); ++j )
      Crashdump_FreeDeviceContext(v12[71] + 376LL * j);
    ExFreePoolWithTag((PVOID)v12[71], 0x43434858u);
  }
  while ( 1 )
  {
    v22 = *v14;
    if ( *v14 == v14 )
      break;
    if ( (_QWORD **)v22[1] != v14 || (v23 = (_QWORD *)*v22, *(_QWORD **)(*v22 + 8LL) != v22) )
      __fastfail(3u);
    *v14 = v23;
    v23[1] = v14;
    CommonBuffer_ReleaseBuffer(v12[61], v22);
  }
  ExFreePoolWithTag(v12, 0x43434858u);
LABEL_36:
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UcxEvtGetDumpData: End 0x%X\n", v13);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140052940  push    rbx
0x140052942  push    rbp
0x140052943  push    rsi
0x140052944  push    rdi
0x140052945  push    r12
0x140052947  push    r13
0x140052949  push    r14
0x14005294b  push    r15
0x14005294d  sub     rsp, 78h
0x140052951  mov     rax, cs:__security_cookie
0x140052958  xor     rax, rsp
0x14005295b  mov     [rsp+0B8h+var_50], rax
0x140052960  xor     eax, eax
0x140052962  mov     [rsp+0B8h+var_88], r8
0x140052967  xorps   xmm0, xmm0
0x14005296a  mov     [rsp+0B8h+var_58], eax
0x14005296e  mov     rbx, rdx
0x140052971  lea     r8, aXhcidumpCrashd_51; "XHCIDUMP: Crashdump_UcxEvtGetDumpData: "...
0x140052978  mov     rdi, rcx
0x14005297b  mov     rbp, r9
0x14005297e  lea     edx, [rax+3]; Level
0x140052981  mov     ecx, 93h; ComponentId
0x140052986  movups  [rsp+0B8h+var_78], xmm0
0x14005298b  movups  [rsp+0B8h+var_68], xmm0
0x140052990  call    cs:__imp_DbgPrintEx
0x140052997  nop     dword ptr [rax+rax+00h]
0x14005299c  mov     rax, cs:WdfFunctions_01033
0x1400529a3  mov     rdx, rbx
0x1400529a6  mov     r8, cs:off_14006C1A8
0x1400529ad  mov     rcx, cs:WdfDriverGlobals
0x1400529b4  mov     rax, [rax+650h]
0x1400529bb  call    _guard_dispatch_icall
0x1400529c0  mov     rcx, cs:WdfFunctions_01033
0x1400529c7  mov     r13, rax
0x1400529ca  mov     r8, cs:off_14006C310
0x1400529d1  mov     rdx, rdi
0x1400529d4  mov     rax, [rcx+650h]
0x1400529db  mov     rcx, cs:WdfDriverGlobals
0x1400529e2  call    _guard_dispatch_icall
0x1400529e7  mov     r14, rax
0x1400529ea  mov     edx, 278h
0x1400529ef  mov     ecx, 40h ; '@'
0x1400529f4  mov     r8d, 43434858h
0x1400529fa  mov     rdi, [rax+58h]
0x1400529fe  mov     rax, [rax+88h]
0x140052a05  mov     r15, [r14+78h]
0x140052a09  mov     [rsp+0B8h+var_80], rax
0x140052a0e  lea     rax, Crashdump_Initialize
0x140052a15  mov     [rbp+10h], rax
0x140052a19  lea     rax, Crashdump_Cleanup
0x140052a20  mov     [rbp+38h], rax
0x140052a24  lea     rax, Crashdump_SendUrb
0x140052a2b  mov     [rbp+18h], rax
0x140052a2f  lea     rax, Crashdump_ResetDevice
0x140052a36  mov     [rbp+30h], rax
0x140052a3a  lea     rax, Crashdump_SendUrbAsync
0x140052a41  mov     [rbp+20h], rax
0x140052a45  lea     rax, Crashdump_PollForCompletion
0x140052a4c  mov     [rbp+28h], rax
0x140052a50  mov     byte ptr [rbp+54h], 0
0x140052a54  call    cs:__imp_ExAllocatePool2
0x140052a5b  nop     dword ptr [rax+rax+00h]
0x140052a60  mov     rbx, rax
0x140052a63  test    rax, rax
0x140052a66  jnz     short loc_140052A72
0x140052a68  mov     edi, 0C000009Ah
0x140052a6d  jmp     loc_140052E2E
0x140052a72  lea     rsi, [rax+1F0h]
0x140052a79  mov     [rsi+8], rsi
0x140052a7d  mov     [rsi], rsi
0x140052a80  mov     [rax+1E8h], r15
0x140052a87  mov     rdx, [r14+88h]
0x140052a8e  mov     [rax], rdi
0x140052a91  movups  xmm0, xmmword ptr [r14+2E0h]
0x140052a99  movdqu  xmmword ptr [rax+8], xmm0
0x140052a9e  mov     eax, [rdi+54h]
0x140052aa1  movzx   ecx, al
0x140052aa4  mov     [rbx+18h], ecx
0x140052aa7  mov     r8d, [rdi+60h]
0x140052aab  mov     [rbx+1Ch], r8d
0x140052aaf  test    r8d, r8d
0x140052ab2  jz      short loc_140052AE0
0x140052ab4  mov     rax, [rdx+30h]
0x140052ab8  mov     rcx, [rax+18h]
0x140052abc  mov     [rbx+20h], rcx
0x140052ac0  mov     rax, [rdx+30h]
0x140052ac4  mov     rcx, [rax+10h]
0x140052ac8  lea     eax, ds:0[r8*8]
0x140052ad0  mov     [rbx+30h], eax
0x140052ad3  mov     [rbx+28h], rcx
0x140052ad7  movups  xmm0, xmmword ptr [rdx+38h]
0x140052adb  movdqu  xmmword ptr [rbx+38h], xmm0
0x140052ae0  lea     rcx, [rbx+48h]
0x140052ae4  mov     rdx, rbx
0x140052ae7  call    Crashdump_EventRing_InitializeForDump
0x140052aec  mov     edi, eax
0x140052aee  test    eax, eax
0x140052af0  js      loc_140052C21
0x140052af6  mov     [rbx+0C8h], rbx
0x140052afd  mov     [rbx+0D0h], rbx
0x140052b04  mov     rax, [rbx]
0x140052b07  mov     rcx, [rax+28h]
0x140052b0b  add     rcx, 20h ; ' '
0x140052b0f  mov     [rbx+0D8h], rcx
0x140052b16  mov     [rbx+148h], rbx
0x140052b1d  mov     [rbx+150h], rbx
0x140052b24  mov     rax, [rbx]
0x140052b27  mov     rcx, [rax+20h]
0x140052b2b  add     rcx, 18h
0x140052b2f  mov     [rbx+158h], rcx
0x140052b36  lea     r8, [rbx+160h]
0x140052b3d  mov     edx, 20h ; ' '
0x140052b42  mov     rcx, rbx
0x140052b45  call    Crashdump_CommonBufferAcquire
0x140052b4a  mov     edi, eax
0x140052b4c  test    eax, eax
0x140052b4e  js      loc_140052C21
0x140052b54  mov     edx, [rbp+50h]
0x140052b57  test    edx, edx
0x140052b59  jz      short loc_140052B89
0x140052b5b  lea     r15, [rbx+250h]
0x140052b62  mov     rcx, rbx
0x140052b65  mov     r8, r15
0x140052b68  call    Crashdump_CommonBufferAcquire
0x140052b6d  mov     edi, eax
0x140052b6f  test    eax, eax
0x140052b71  js      loc_140052C21
0x140052b77  mov     rax, [rbx+258h]
0x140052b7e  mov     [rbp+40h], rax
0x140052b82  mov     rax, [r15]
0x140052b85  mov     [rbp+48h], rax
0x140052b89  mov     eax, [r13+14h]
0x140052b8d  lea     r12, [rbx+220h]
0x140052b94  mov     [rbx+20Ch], eax
0x140052b9a  movups  xmm0, xmmword ptr [r13+20h]
0x140052b9f  movups  xmmword ptr [rbx+214h], xmm0
0x140052ba6  movups  xmm1, xmmword ptr [r13+30h]
0x140052bab  movups  xmmword ptr [rbx+224h], xmm1
0x140052bb2  mov     eax, [r13+40h]
0x140052bb6  mov     [rbx+234h], eax
0x140052bbc  mov     eax, [r12]
0x140052bc0  dec     eax
0x140052bc2  imul    rdx, rax, 78h ; 'x'
0x140052bc6  mov     rax, [r14+98h]
0x140052bcd  mov     rcx, [rax+30h]
0x140052bd1  mov     eax, 14h
0x140052bd6  cmp     byte ptr [rdx+rcx+0Dh], 2
0x140052bdb  lea     r8d, [rax+0Ah]
0x140052bdf  lea     ecx, [r8+22h]
0x140052be3  cmovnz  eax, r8d
0x140052be7  mov     r8d, 43434858h
0x140052bed  mov     [rbx+210h], eax
0x140052bf3  mov     eax, [rbx+218h]
0x140052bf9  imul    rdx, rax, 178h
0x140052c00  call    cs:__imp_ExAllocatePool2
0x140052c07  nop     dword ptr [rax+rax+00h]
0x140052c0c  mov     [rbx+238h], rax
0x140052c13  test    rax, rax
0x140052c16  jnz     loc_140052CA4
0x140052c1c  mov     edi, 0C000009Ah
0x140052c21  cmp     qword ptr [rbx+238h], 0
0x140052c29  jz      short loc_140052C6C
0x140052c2b  xor     ebp, ebp
0x140052c2d  cmp     [rbx+218h], ebp
0x140052c33  jbe     short loc_140052C54
0x140052c35  mov     eax, ebp
0x140052c37  imul    rcx, rax, 178h
0x140052c3e  add     rcx, [rbx+238h]
0x140052c45  call    Crashdump_FreeDeviceContext
0x140052c4a  inc     ebp
0x140052c4c  cmp     ebp, [rbx+218h]
0x140052c52  jb      short loc_140052C35
0x140052c54  mov     rcx, [rbx+238h]; P
0x140052c5b  mov     edx, 43434858h; Tag
0x140052c60  call    cs:__imp_ExFreePoolWithTag
0x140052c67  nop     dword ptr [rax+rax+00h]
0x140052c6c  mov     rdx, [rsi]
0x140052c6f  cmp     rdx, rsi
0x140052c72  jz      loc_140052E1A
0x140052c78  cmp     [rdx+8], rsi
0x140052c7c  jnz     loc_140052E13
0x140052c82  mov     rax, [rdx]
0x140052c85  cmp     [rax+8], rdx
0x140052c89  jnz     loc_140052E13
0x140052c8f  mov     [rsi], rax
0x140052c92  mov     [rax+8], rsi
0x140052c96  mov     rcx, [rbx+1E8h]
0x140052c9d  call    CommonBuffer_ReleaseBuffer
0x140052ca2  jmp     short loc_140052C6C
0x140052ca4  mov     r13, [rsp+0B8h+var_88]
0x140052ca9  xor     edi, edi
0x140052cab  mov     eax, [rbx+218h]
0x140052cb1  cmp     edi, eax
0x140052cb3  jnb     short loc_140052D2B
0x140052cb5  xorps   xmm0, xmm0
0x140052cb8  lea     r15d, [rdi+1]
0x140052cbc  xor     eax, eax
0x140052cbe  mov     r8d, r15d
0x140052cc1  movups  [rsp+0B8h+var_78], xmm0
0x140052cc6  shl     r8, 2; Size
0x140052cca  lea     rcx, [rsp+0B8h+var_78+0Ch]; void *
0x140052ccf  mov     rdx, r12; Src
0x140052cd2  mov     [rsp+0B8h+var_58], eax
0x140052cd6  movups  [rsp+0B8h+var_68], xmm0
0x140052cdb  mov     dword ptr [rsp+0B8h+var_78+4], r15d
0x140052ce0  call    memmove
0x140052ce5  mov     eax, edi
0x140052ce7  lea     r9, [rsp+0B8h+var_78]
0x140052cec  imul    rcx, rax, 178h
0x140052cf3  xor     eax, eax
0x140052cf5  mov     r8, r13
0x140052cf8  add     rcx, [rbx+238h]
0x140052cff  mov     rdx, rbx
0x140052d02  cmp     r15d, [rbx+218h]
0x140052d09  mov     [rsp+0B8h+var_98], rcx
0x140052d0e  mov     rcx, [rsp+0B8h+var_80]
0x140052d13  cmovnz  r8, rax
0x140052d17  call    Crashdump_InitializeDeviceContext
0x140052d1c  mov     edi, eax
0x140052d1e  test    eax, eax
0x140052d20  js      loc_140052C21
0x140052d26  mov     edi, r15d
0x140052d29  jmp     short loc_140052CAB
0x140052d2b  lea     ecx, [rax-1]
0x140052d2e  mov     edx, 40h ; '@'
0x140052d33  imul    rax, rcx, 178h
0x140052d3a  lea     r8, [rbx+1B8h]
0x140052d41  mov     rcx, rbx
0x140052d44  add     rax, [rbx+238h]
0x140052d4b  mov     [rbx+240h], rax
0x140052d52  call    Crashdump_CommonBufferAcquire
0x140052d57  mov     edi, eax
0x140052d59  test    eax, eax
0x140052d5b  js      loc_140052C21
0x140052d61  mov     rax, [rbx]
0x140052d64  lea     r8, [rbx+1D0h]
0x140052d6b  mov     edx, 840h
0x140052d70  mov     ecx, [rax+68h]
0x140052d73  test    cl, 4
0x140052d76  mov     rcx, rbx
0x140052d79  jnz     short loc_140052D80
0x140052d7b  mov     edx, 420h
0x140052d80  call    Crashdump_CommonBufferAcquire
0x140052d85  mov     edi, eax
0x140052d87  test    eax, eax
0x140052d89  js      loc_140052C21
0x140052d8f  mov     edx, [rbx+218h]
0x140052d95  lea     r8, [rbx+1A0h]
0x140052d9c  mov     [rbx+198h], edx
0x140052da2  mov     rcx, rbx
0x140052da5  lea     edx, ds:8[rdx*8]
0x140052dac  call    Crashdump_CommonBufferAcquire
0x140052db1  mov     edi, eax
0x140052db3  test    eax, eax
0x140052db5  js      loc_140052C21
0x140052dbb  mov     r9d, [rbx+200h]
0x140052dc2  lea     r8, aXhcidumpCommon_0; "XHCIDUMP: CommonBuffer: Allocated %u pa"...
0x140052dc9  mov     eax, [rbx+204h]
0x140052dcf  mov     ecx, r9d
0x140052dd2  shl     ecx, 0Ch
0x140052dd5  mov     edx, 3; Level
0x140052dda  mov     [rsp+0B8h+var_90], eax
0x140052dde  mov     dword ptr [rsp+0B8h+var_98], ecx
0x140052de2  mov     ecx, 93h; ComponentId
0x140052de7  call    cs:__imp_DbgPrintEx
0x140052dee  nop     dword ptr [rax+rax+00h]
0x140052df3  mov     dword ptr [rbx+248h], 0
0x140052dfd  xor     edi, edi
0x140052dff  mov     [rbp+8], rbx
0x140052e03  mov     [rbx+268h], r14
0x140052e0a  mov     [r14+338h], rbx
0x140052e11  jmp     short loc_140052E2E
0x140052e13  mov     ecx, 3
0x140052e18  int     29h; Win8: RtlFailFast(ecx)
0x140052e1a  mov     edx, 43434858h; Tag
0x140052e1f  mov     rcx, rbx; P
0x140052e22  call    cs:__imp_ExFreePoolWithTag
0x140052e29  nop     dword ptr [rax+rax+00h]
0x140052e2e  mov     r9d, edi
0x140052e31  lea     r8, aXhcidumpCrashd_45; "XHCIDUMP: Crashdump_UcxEvtGetDumpData: "...
0x140052e38  mov     edx, 3; Level
0x140052e3d  mov     ecx, 93h; ComponentId
0x140052e42  call    cs:__imp_DbgPrintEx
0x140052e49  nop     dword ptr [rax+rax+00h]
0x140052e4e  mov     eax, edi
0x140052e50  mov     rcx, [rsp+0B8h+var_50]
0x140052e55  xor     rcx, rsp; StackCookie
0x140052e58  call    __security_check_cookie
0x140052e5d  add     rsp, 78h
0x140052e61  pop     r15
0x140052e63  pop     r14
0x140052e65  pop     r13
0x140052e67  pop     r12
0x140052e69  pop     rdi
0x140052e6a  pop     rsi
0x140052e6b  pop     rbp
0x140052e6c  pop     rbx
0x140052e6d  retn
```
