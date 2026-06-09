# SdbpOpenCompressedDatabase

- ea: `0x140031938`
- end: `0x140031aa3`
- name: `SdbpOpenCompressedDatabase`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140042ad4`

## callees

- `0x140007ad0`
- `0x14002e118`
- `0x140031938`
- `0x14003e364`
- `0x140044fc8`
- `0x140045d44`
- `0x14005498c`

## string_xrefs

- `0x14003196d`: `SdbpOpenCompressedDatabase`
- `0x140031a34`: `SdbpOpenCompressedDatabase`
- `0x1400319a8`: `SDB is not compressed`
- `0x1400319c2`: `SDB compression algorithm does not match callback algorithm.`
- `0x1400319ed`: `SdbpOpenCompressedDatabase failed to allocate expanded buffer - out of memory`

## pseudocode

```c
__int64 __fastcall SdbpOpenCompressedDatabase(_QWORD *a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // edi
  _DWORD *v4; // rbx
  __int64 v7; // rbp
  _DWORD *v8; // rcx
  void *v9; // r14
  __int64 v10; // rcx
  __int64 result; // rax
  _DWORD *v12; // rax
  unsigned int v13; // [rsp+78h] [rbp+10h] BYREF
  int v14; // [rsp+7Ch] [rbp+14h]

  v14 = HIDWORD(a2);
  v3 = 0;
  v4 = 0;
  v13 = 0;
  if ( !g_ExpandCallback )
  {
    AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 175, "No expand callback method set. Cannot expand ZDB file.");
    goto LABEL_16;
  }
  v7 = *a1;
  if ( *(_DWORD *)(*a1 + 20LL) >= 0x14u )
  {
    v8 = *(_DWORD **)(v7 + 8);
    if ( v8[2] == 1717724282 )
    {
      if ( v8[3] == g_ExpectedAlgorithm )
      {
        v13 = v8[4];
        v9 = (void *)AslAlloc((__int64)v8, v13, 1);
        if ( v9 )
        {
          if ( (unsigned int)((__int64 (__fastcall *)(void *, unsigned int *, __int64, _QWORD))g_ExpandCallback)(
                               v9,
                               &v13,
                               *(_QWORD *)(v7 + 8) + 20LL,
                               (unsigned int)(*(_DWORD *)(v7 + 20) - 20)) )
          {
            v12 = SdbpOpenDatabaseInMemory((__int64)v9, v13, a3);
            v4 = v12;
            if ( v12 )
            {
              v12[6] |= 0xCu;
              v3 = 1;
              v13 = 0;
              goto LABEL_16;
            }
          }
          else
          {
            AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 221, "Expand callback failed to expand SDB");
          }
          AslFree(v10, v9);
          v13 = 0;
          if ( v4 )
          {
            SdbCloseDatabaseRead(v4);
            v4 = 0;
          }
        }
        else
        {
          AslLogCallPrintf(
            1,
            "SdbpOpenCompressedDatabase",
            211,
            "SdbpOpenCompressedDatabase failed to allocate expanded buffer - out of memory");
        }
      }
      else
      {
        AslLogCallPrintf(
          1,
          "SdbpOpenCompressedDatabase",
          192,
          "SDB compression algorithm does not match callback algorithm.");
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 187, "SDB is not compressed");
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 180, "SDB file too small to be valid");
  }
LABEL_16:
  SdbCloseDatabaseRead(*a1);
  result = v3;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x140031938  mov     [rsp+arg_8], rdx
0x14003193d  push    rbx
0x14003193e  push    rbp
0x14003193f  push    rsi
0x140031940  push    rdi
0x140031941  push    r14
0x140031943  push    r15
0x140031945  sub     rsp, 38h
0x140031949  xor     edi, edi
0x14003194b  xor     ebx, ebx
0x14003194d  cmp     cs:g_ExpandCallback, rbx
0x140031954  mov     r15d, r8d
0x140031957  mov     rsi, rcx
0x14003195a  mov     dword ptr [rsp+68h+arg_8], edi
0x14003195e  jnz     short loc_140031983
0x140031960  lea     r9, aNoExpandCallba; "No expand callback method set. Cannot e"...
0x140031967  mov     r8d, 0AFh
0x14003196d  lea     rdx, aSdbpopencompre_0; "SdbpOpenCompressedDatabase"
0x140031974  mov     ecx, 1
0x140031979  call    AslLogCallPrintf
0x14003197e  jmp     loc_140031A5E
0x140031983  mov     rbp, [rcx]
0x140031986  cmp     dword ptr [rbp+14h], 14h
0x14003198a  jnb     short loc_14003199B
0x14003198c  lea     r9, aSdbFileTooSmal; "SDB file too small to be valid"
0x140031993  mov     r8d, 0B4h
0x140031999  jmp     short loc_14003196D
0x14003199b  mov     rcx, [rbp+8]
0x14003199f  cmp     dword ptr [rcx+8], 6662647Ah
0x1400319a6  jz      short loc_1400319B7
0x1400319a8  lea     r9, aSdbIsNotCompre; "SDB is not compressed"
0x1400319af  mov     r8d, 0BBh
0x1400319b5  jmp     short loc_14003196D
0x1400319b7  mov     eax, cs:g_ExpectedAlgorithm
0x1400319bd  cmp     [rcx+0Ch], eax
0x1400319c0  jz      short loc_1400319D1
0x1400319c2  lea     r9, aSdbCompression; "SDB compression algorithm does not matc"...
0x1400319c9  mov     r8d, 0C0h
0x1400319cf  jmp     short loc_14003196D
0x1400319d1  mov     eax, [rcx+10h]
0x1400319d4  mov     r8d, 1
0x1400319da  mov     edx, eax
0x1400319dc  mov     dword ptr [rsp+68h+arg_8], eax
0x1400319e0  call    AslAlloc
0x1400319e5  mov     r14, rax
0x1400319e8  test    rax, rax
0x1400319eb  jnz     short loc_1400319FF
0x1400319ed  lea     r9, aSdbpopencompre_1; "SdbpOpenCompressedDatabase failed to al"...
0x1400319f4  mov     r8d, 0D3h
0x1400319fa  jmp     loc_14003196D
0x1400319ff  mov     r9d, [rbp+14h]
0x140031a03  lea     rdx, [rsp+68h+arg_8]
0x140031a08  mov     r8, [rbp+8]
0x140031a0c  sub     r9d, 14h
0x140031a10  mov     rax, cs:g_ExpandCallback
0x140031a17  add     r8, 14h
0x140031a1b  mov     rcx, r14
0x140031a1e  call    _guard_dispatch_icall
0x140031a23  test    eax, eax
0x140031a25  jnz     short loc_140031A79
0x140031a27  lea     r9, aExpandCallback; "Expand callback failed to expand SDB"
0x140031a2e  mov     r8d, 0DDh
0x140031a34  lea     rdx, aSdbpopencompre_0; "SdbpOpenCompressedDatabase"
0x140031a3b  lea     ecx, [rax+1]
0x140031a3e  call    AslLogCallPrintf
0x140031a43  mov     rdx, r14
0x140031a46  call    AslFree
0x140031a4b  mov     dword ptr [rsp+68h+arg_8], edi
0x140031a4f  test    rbx, rbx
0x140031a52  jz      short loc_140031A5E
0x140031a54  mov     rcx, rbx
0x140031a57  call    SdbCloseDatabaseRead
0x140031a5c  xor     ebx, ebx
0x140031a5e  mov     rcx, [rsi]
0x140031a61  call    SdbCloseDatabaseRead
0x140031a66  mov     eax, edi
0x140031a68  mov     [rsi], rbx
0x140031a6b  add     rsp, 38h
0x140031a6f  pop     r15
0x140031a71  pop     r14
0x140031a73  pop     rdi
0x140031a74  pop     rsi
0x140031a75  pop     rbp
0x140031a76  pop     rbx
0x140031a77  retn
0x140031a79  mov     edx, dword ptr [rsp+68h+arg_8]
0x140031a7d  mov     r8d, r15d
0x140031a80  mov     rcx, r14
0x140031a83  call    SdbpOpenDatabaseInMemory
0x140031a88  mov     rbx, rax
0x140031a8b  test    rax, rax
0x140031a8e  jz      short loc_140031A43
0x140031a90  or      dword ptr [rax+18h], 0Ch
0x140031a94  mov     edi, 1
0x140031a99  mov     dword ptr [rsp+68h+arg_8], 0
0x140031aa1  jmp     short loc_140031A5E
```
