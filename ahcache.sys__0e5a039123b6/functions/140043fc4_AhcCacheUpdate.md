# AhcCacheUpdate

- ea: `0x140043fc4`
- end: `0x1400440d2`
- name: `AhcCacheUpdate`
- size: `270`
- prototype: `__int64 __fastcall(__int64, int, void *, unsigned int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140045a00`

## callees

- `0x14003e364`
- `0x140043858`
- `0x140043bb0`
- `0x140043f88`
- `0x140043fc4`
- `0x14004545c`

## string_xrefs

- `0x140044071`: `AhcCacheUpdate`
- `0x140044098`: `AhcCacheUpdate`
- `0x1400440bc`: `AhcCacheUpdate`
- `0x140044087`: `Failed to acquire entry for Update [%x]`
- `0x1400440ab`: `Failed to update entry [%x]`

## pseudocode

```c
__int64 __fastcall AhcCacheUpdate(__int64 a1, int a2, void *a3, unsigned int a4, __int64 a5, unsigned int a6)
{
  int v10; // eax
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  int v15[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v16; // [rsp+70h] [rbp+8h] BYREF

  v16 = 0;
  *(_QWORD *)v15 = 0;
  v10 = AhcQuirksInit(a1);
  if ( v10 < 0 )
    AslLogCallPrintf(1, "AhcCacheUpdate", 1951, "Failed to initialize quirks [%x]", v10);
  v11 = AhcpCacheEntryAcquire((int)&v16, (int)v15, *(_QWORD *)(a1 + 24), a2, a3, 1);
  v12 = v11;
  if ( v11 < 0 )
  {
    AslLogCallPrintf(1, "AhcCacheUpdate", 1964, "Failed to acquire entry for Update [%x]", v11);
  }
  else
  {
    v13 = AhcpCacheEntryUpdate(v16, a4, a5, a6);
    v12 = v13;
    if ( v13 < 0 )
      AslLogCallPrintf(1, "AhcCacheUpdate", 1975, "Failed to update entry [%x]", v13);
    else
      v12 = 0;
    AhcpCacheEntryReleaseForWrite(*(_QWORD *)(a1 + 24), v16, *(_QWORD *)v15);
  }
  return v12;
}

```

## disassembly

```asm
0x140043fc4  push    rbx
0x140043fc6  push    rbp
0x140043fc7  push    rsi
0x140043fc8  push    rdi
0x140043fc9  sub     rsp, 48h
0x140043fcd  mov     esi, r9d
0x140043fd0  mov     [rsp+68h+arg_0], 0
0x140043fd9  mov     rbx, r8
0x140043fdc  mov     qword ptr [rsp+68h+var_38], 0
0x140043fe5  mov     rbp, rdx
0x140043fe8  mov     rdi, rcx
0x140043feb  call    AhcQuirksInit
0x140043ff0  test    eax, eax
0x140043ff2  js      short loc_140044060
0x140043ff4  mov     r8, [rdi+18h]; int
0x140043ff8  lea     rdx, [rsp+68h+var_38]; int
0x140043ffd  mov     [rsp+68h+var_40], 1; int
0x140044005  lea     rcx, [rsp+68h+arg_0]; int
0x14004400a  mov     r9, rbp; int
0x14004400d  mov     [rsp+68h+FileHandle], rbx; FileHandle
0x140044012  call    AhcpCacheEntryAcquire
0x140044017  mov     ebx, eax
0x140044019  test    eax, eax
0x14004401b  js      short loc_140044087
0x14004401d  mov     r9d, [rsp+68h+arg_28]
0x140044025  mov     edx, esi
0x140044027  mov     r8, [rsp+68h+arg_20]
0x14004402f  mov     rcx, [rsp+68h+arg_0]
0x140044034  call    AhcpCacheEntryUpdate
0x140044039  mov     ebx, eax
0x14004403b  test    eax, eax
0x14004403d  js      short loc_1400440AB
0x14004403f  xor     ebx, ebx
0x140044041  mov     r8, qword ptr [rsp+68h+var_38]
0x140044046  mov     rdx, [rsp+68h+arg_0]
0x14004404b  mov     rcx, [rdi+18h]
0x14004404f  call    AhcpCacheEntryReleaseForWrite
0x140044054  mov     eax, ebx
0x140044056  add     rsp, 48h
0x14004405a  pop     rdi
0x14004405b  pop     rsi
0x14004405c  pop     rbp
0x14004405d  pop     rbx
0x14004405e  retn
0x140044060  lea     r9, aFailedToInitia_4; "Failed to initialize quirks [%x]"
0x140044067  mov     dword ptr [rsp+68h+FileHandle], eax
0x14004406b  mov     r8d, 79Fh
0x140044071  lea     rdx, aAhccacheupdate; "AhcCacheUpdate"
0x140044078  mov     ecx, 1
0x14004407d  call    AslLogCallPrintf
0x140044082  jmp     loc_140043FF4
0x140044087  lea     r9, aFailedToAcquir_4; "Failed to acquire entry for Update [%x]"
0x14004408e  mov     dword ptr [rsp+68h+FileHandle], eax
0x140044092  mov     r8d, 7ACh
0x140044098  lea     rdx, aAhccacheupdate; "AhcCacheUpdate"
0x14004409f  mov     ecx, 1
0x1400440a4  call    AslLogCallPrintf
0x1400440a9  jmp     short loc_140044054
0x1400440ab  lea     r9, aFailedToUpdate_0; "Failed to update entry [%x]"
0x1400440b2  mov     dword ptr [rsp+68h+FileHandle], eax
0x1400440b6  mov     r8d, 7B7h
0x1400440bc  lea     rdx, aAhccacheupdate; "AhcCacheUpdate"
0x1400440c3  mov     ecx, 1
0x1400440c8  call    AslLogCallPrintf
0x1400440cd  jmp     loc_140044041
```
