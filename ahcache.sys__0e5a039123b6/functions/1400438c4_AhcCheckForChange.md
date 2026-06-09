# AhcCheckForChange

- ea: `0x1400438c4`
- end: `0x140043a76`
- name: `AhcCheckForChange`
- size: `434`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x14002b128`
- `0x1400436f8`
- `0x14004c3a0`

## callees

- `0x1400256f8`
- `0x140025ea8`
- `0x1400260f8`
- `0x140027d34`
- `0x140029954`
- `0x14002a898`
- `0x14003e364`
- `0x1400438c4`
- `0x1400591c4`

## string_xrefs

- `0x14004397f`: `Failed to clear cache apphelp data [%x]`
- `0x1400439bf`: `Failed to save statistics and cache to registry [%x]`
- `0x140043a00`: `Failed to save cdb store to registry [%x]`
- `0x140043a20`: `Failed to save sdb timestamp to registry [%x]`
- `0x140043a54`: `Failed to update quirks table after servicing [%x]`

## pseudocode

```c
__int64 __fastcall AhcCheckForChange(__int64 a1, _DWORD *a2)
{
  unsigned __int64 v4; // rcx
  int inited; // eax
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 v8; // r8
  int v9; // ebp
  int v10; // eax
  _DWORD *v11; // rdx
  int v13; // [rsp+60h] [rbp+8h] BYREF

  v13 = 0;
  v4 = (unsigned __int64)MEMORY[0xFFFFF78000000004] << 32;
  if ( (unsigned __int64)(((v4 * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64)
                        - *(_QWORD *)(a1 + 120)) <= *(_QWORD *)(a1 + 112)
    && !a2[1] )
  {
    *a2 = 0;
    return 0;
  }
  *(_QWORD *)(a1 + 120) = (v4 * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64;
  inited = AhcCdbDetectServicing(&v13, *(_QWORD *)(a1 + 32));
  v6 = inited;
  if ( inited >= 0 )
  {
    v9 = v13;
    if ( !v13 )
    {
      *a2 = 0;
      return v6;
    }
    inited = AhcCacheClear(*(_QWORD *)(a1 + 24), 4294922399LL);
    v6 = inited;
    if ( inited >= 0 )
    {
      v10 = *(_DWORD *)(a1 + 56);
      *(_OWORD *)(a1 + 40) = 0;
      *(_OWORD *)(a1 + 56) = 0;
      *(_OWORD *)(a1 + 72) = 0;
      *(_DWORD *)(a1 + 88) = 0;
      *(_DWORD *)(a1 + 40) = 52;
      *(_DWORD *)(a1 + 56) = v10 + 1;
      inited = AhcCacheWriteRegistry(a1);
      v6 = inited;
      if ( inited >= 0 )
      {
        inited = AhcCdbRefresh(*(_QWORD *)(a1 + 32));
        v6 = inited;
        if ( inited >= 0 )
        {
          inited = AhcCdbWriteRegistry(a1);
          v6 = inited;
          if ( inited >= 0 )
          {
            inited = AhcCdbPersistTimeStamps(a1);
            v6 = inited;
            if ( inited >= 0 )
            {
              if ( !*(_DWORD *)(a1 + 100)
                || (!a2[2] ? (v11 = 0) : (v11 = a2 + 4), inited = AhcQuirksInitTable(a1, v11), v6 = inited, inited >= 0) )
              {
                *a2 = v9;
                return 0;
              }
              v7 = "Failed to update quirks table after servicing [%x]";
              v8 = 583;
            }
            else
            {
              v7 = "Failed to save sdb timestamp to registry [%x]";
              v8 = 560;
            }
          }
          else
          {
            v7 = "Failed to save cdb store to registry [%x]";
            v8 = 553;
          }
        }
        else
        {
          v7 = "Failed to refresh cdb store [%x]";
          v8 = 542;
        }
      }
      else
      {
        v7 = "Failed to save statistics and cache to registry [%x]";
        v8 = 535;
      }
    }
    else
    {
      v7 = "Failed to clear cache apphelp data [%x]";
      v8 = 515;
    }
  }
  else
  {
    v7 = "Failed to detect sdb servicing [%x]";
    v8 = 500;
  }
  AslLogCallPrintf(1, "AhcCheckForChange", v8, v7, inited);
  return v6;
}

```

## disassembly

```asm
0x1400438c4  push    rbx
0x1400438c6  push    rbp
0x1400438c7  push    rsi
0x1400438c8  push    rdi
0x1400438c9  sub     rsp, 38h
0x1400438cd  mov     rdi, rcx
0x1400438d0  mov     [rsp+58h+arg_0], 0
0x1400438d8  mov     rax, 0FFFFF78000000004h
0x1400438e2  mov     rsi, rdx
0x1400438e5  mov     ecx, [rax]
0x1400438e7  mov     rax, 0FFFFF78000000320h
0x1400438f1  shl     rcx, 20h
0x1400438f5  mov     rax, [rax]
0x1400438f8  shl     rax, 8
0x1400438fc  mul     rcx
0x1400438ff  mov     rax, rdx
0x140043902  sub     rax, [rdi+78h]
0x140043906  cmp     rax, [rdi+70h]
0x14004390a  ja      short loc_14004391D
0x14004390c  cmp     dword ptr [rsi+4], 0
0x140043910  jnz     short loc_14004391D
0x140043912  mov     dword ptr [rsi], 0
0x140043918  jmp     loc_140043A68
0x14004391d  mov     [rdi+78h], rdx
0x140043921  lea     rcx, [rsp+58h+arg_0]
0x140043926  mov     rdx, [rdi+20h]
0x14004392a  call    AhcCdbDetectServicing
0x14004392f  mov     ebx, eax
0x140043931  test    eax, eax
0x140043933  jns     short loc_14004395C
0x140043935  lea     r9, aFailedToDetect; "Failed to detect sdb servicing [%x]"
0x14004393c  mov     r8d, 1F4h
0x140043942  lea     rdx, aAhccheckforcha; "AhcCheckForChange"
0x140043949  mov     [rsp+58h+var_38], eax
0x14004394d  mov     ecx, 1
0x140043952  call    AslLogCallPrintf
0x140043957  jmp     loc_140043A6A
0x14004395c  mov     ebp, [rsp+58h+arg_0]
0x140043960  test    ebp, ebp
0x140043962  jnz     short loc_14004396B
0x140043964  mov     [rsi], ebp
0x140043966  jmp     loc_140043A6A
0x14004396b  mov     rcx, [rdi+18h]
0x14004396f  mov     edx, 0FFFF509Fh
0x140043974  call    AhcCacheClear
0x140043979  mov     ebx, eax
0x14004397b  test    eax, eax
0x14004397d  jns     short loc_14004398E
0x14004397f  lea     r9, aFailedToClearC_1; "Failed to clear cache apphelp data [%x]"
0x140043986  mov     r8d, 203h
0x14004398c  jmp     short loc_140043942
0x14004398e  mov     eax, [rdi+38h]
0x140043991  xorps   xmm0, xmm0
0x140043994  movups  xmmword ptr [rdi+28h], xmm0
0x140043998  xor     ecx, ecx
0x14004399a  inc     eax
0x14004399c  movups  xmmword ptr [rdi+38h], xmm0
0x1400439a0  movups  xmmword ptr [rdi+48h], xmm0
0x1400439a4  mov     [rdi+58h], ecx
0x1400439a7  mov     rcx, rdi
0x1400439aa  mov     dword ptr [rdi+28h], 34h ; '4'
0x1400439b1  mov     [rdi+38h], eax
0x1400439b4  call    AhcCacheWriteRegistry
0x1400439b9  mov     ebx, eax
0x1400439bb  test    eax, eax
0x1400439bd  jns     short loc_1400439D1
0x1400439bf  lea     r9, aFailedToSaveSt_1; "Failed to save statistics and cache to "...
0x1400439c6  mov     r8d, 217h
0x1400439cc  jmp     loc_140043942
0x1400439d1  mov     rcx, [rdi+20h]
0x1400439d5  call    AhcCdbRefresh
0x1400439da  mov     ebx, eax
0x1400439dc  test    eax, eax
0x1400439de  jns     short loc_1400439F2
0x1400439e0  lea     r9, aFailedToRefres; "Failed to refresh cdb store [%x]"
0x1400439e7  mov     r8d, 21Eh
0x1400439ed  jmp     loc_140043942
0x1400439f2  mov     rcx, rdi
0x1400439f5  call    AhcCdbWriteRegistry
0x1400439fa  mov     ebx, eax
0x1400439fc  test    eax, eax
0x1400439fe  jns     short loc_140043A12
0x140043a00  lea     r9, aFailedToSaveCd_0; "Failed to save cdb store to registry [%"...
0x140043a07  mov     r8d, 229h
0x140043a0d  jmp     loc_140043942
0x140043a12  mov     rcx, rdi
0x140043a15  call    AhcCdbPersistTimeStamps
0x140043a1a  mov     ebx, eax
0x140043a1c  test    eax, eax
0x140043a1e  jns     short loc_140043A32
0x140043a20  lea     r9, aFailedToSaveSd; "Failed to save sdb timestamp to registr"...
0x140043a27  mov     r8d, 230h
0x140043a2d  jmp     loc_140043942
0x140043a32  cmp     dword ptr [rdi+64h], 0
0x140043a36  jz      short loc_140043A66
0x140043a38  cmp     dword ptr [rsi+8], 0
0x140043a3c  jz      short loc_140043A44
0x140043a3e  lea     rdx, [rsi+10h]
0x140043a42  jmp     short loc_140043A46
0x140043a44  xor     edx, edx
0x140043a46  mov     rcx, rdi
0x140043a49  call    AhcQuirksInitTable
0x140043a4e  mov     ebx, eax
0x140043a50  test    eax, eax
0x140043a52  jns     short loc_140043A66
0x140043a54  lea     r9, aFailedToUpdate; "Failed to update quirks table after ser"...
0x140043a5b  mov     r8d, 247h
0x140043a61  jmp     loc_140043942
0x140043a66  mov     [rsi], ebp
0x140043a68  xor     ebx, ebx
0x140043a6a  mov     eax, ebx
0x140043a6c  add     rsp, 38h
0x140043a70  pop     rdi
0x140043a71  pop     rsi
0x140043a72  pop     rbp
0x140043a73  pop     rbx
0x140043a74  retn
```
