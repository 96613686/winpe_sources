# pDrvRecoveryCreateInfo(HDRIVERSTORE__ *,ushort const *,ulong,_DRVRECOVERY_INFO * *)

- ea: `0x18003b3f4`
- end: `0x18003b4ef`
- name: `?pDrvRecoveryCreateInfo@@YAHPEAUHDRIVERSTORE__@@PEBGKPEAPEAU_DRVRECOVERY_INFO@@@Z`
- size: `251`
- prototype: `int(struct HDRIVERSTORE__ *, const unsigned __int16 *, unsigned int, struct _DRVRECOVERY_INFO **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003abbc`

## callees

- `0x180007720`
- `0x18001ba48`
- `0x18003b3f4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b4c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b4c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003b42e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003b42e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b4d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b4d3`
- `DEVRTL!DevRtlCreateTextLogSectionW` at `0x18003b4a8`
- `DEVRTL!DevRtlCreateTextLogSectionW` at `0x18003b4a8`

## pseudocode

```c
_BOOL8 __fastcall pDrvRecoveryCreateInfo(
        struct HDRIVERSTORE__ *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct _DRVRECOVERY_INFO **a4)
{
  size_t v4; // rsi
  DWORD v8; // edi
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbx

  v4 = a3;
  if ( a3 >= 0x2B8 )
  {
    v9 = (unsigned __int16 *)HeapAlloc(hHeap, 0, a3);
    v10 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, v4);
      if ( (int)StringCchCopyW(v10 + 8, 0x104u, a2) < 0 )
      {
        HeapFree(hHeap, 0, v10);
        v8 = 13;
      }
      else
      {
        *(_DWORD *)v10 = v4;
        v8 = 0;
        *((_QWORD *)v10 + 1) = a1;
        *((_DWORD *)v10 + 150) = -1;
        *((_DWORD *)v10 + 151) = -1;
        *((_DWORD *)v10 + 144) = -1;
        *((_DWORD *)v10 + 145) = -1;
        *((_QWORD *)v10 + 73) = 0;
        if ( !(unsigned int)DevRtlCreateTextLogSectionW(v10 + 8, 3, L"Driver Recovery", v10 + 280) )
          *((_QWORD *)v10 + 70) = 0;
        *a4 = (struct _DRVRECOVERY_INFO *)v10;
      }
    }
    else
    {
      v8 = 8;
    }
  }
  else
  {
    v8 = 87;
  }
  SetLastError(v8);
  return v8 == 0;
}

```

## disassembly

```asm
0x18003b3f4  push    rbx
0x18003b3f6  push    rbp
0x18003b3f7  push    rsi
0x18003b3f8  push    rdi
0x18003b3f9  push    r12
0x18003b3fb  push    r14
0x18003b3fd  push    r15
0x18003b3ff  sub     rsp, 20h
0x18003b403  mov     esi, r8d
0x18003b406  mov     r14, r9
0x18003b409  mov     rbp, rdx
0x18003b40c  mov     r12, rcx
0x18003b40f  cmp     r8d, 2B8h
0x18003b416  jnb     short loc_18003B422
0x18003b418  mov     edi, 57h ; 'W'
0x18003b41d  jmp     loc_18003B4D1
0x18003b422  mov     rcx, cs:hHeap; hHeap
0x18003b429  mov     r8, rsi; dwBytes
0x18003b42c  xor     edx, edx; dwFlags
0x18003b42e  call    cs:__imp_HeapAlloc
0x18003b434  mov     rbx, rax
0x18003b437  test    rax, rax
0x18003b43a  jnz     short loc_18003B444
0x18003b43c  lea     edi, [rax+8]
0x18003b43f  jmp     loc_18003B4D1
0x18003b444  mov     r8, rsi; Size
0x18003b447  xor     edx, edx; Val
0x18003b449  mov     rcx, rbx; void *
0x18003b44c  call    memset_0
0x18003b451  mov     r8, rbp; unsigned __int16 *
0x18003b454  lea     rcx, [rbx+10h]; unsigned __int16 *
0x18003b458  mov     edx, 104h; unsigned __int64
0x18003b45d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003b462  test    eax, eax
0x18003b464  js      short loc_18003B4BA
0x18003b466  or      eax, 0FFFFFFFFh
0x18003b469  mov     [rbx], esi
0x18003b46b  xor     edi, edi
0x18003b46d  mov     [rbx+8], r12
0x18003b471  lea     rsi, [rbx+230h]
0x18003b478  mov     [rbx+258h], eax
0x18003b47e  mov     r9, rsi
0x18003b481  mov     [rbx+25Ch], eax
0x18003b487  lea     r8, aDriverRecovery_0; "Driver Recovery"
0x18003b48e  mov     [rbx+240h], eax
0x18003b494  lea     edx, [rdi+3]
0x18003b497  mov     [rbx+244h], eax
0x18003b49d  lea     rcx, [rbx+10h]
0x18003b4a1  mov     [rbx+248h], rdi
0x18003b4a8  call    cs:__imp_DevRtlCreateTextLogSectionW
0x18003b4ae  test    eax, eax
0x18003b4b0  jnz     short loc_18003B4B5
0x18003b4b2  mov     [rsi], rdi
0x18003b4b5  mov     [r14], rbx
0x18003b4b8  jmp     short loc_18003B4D1
0x18003b4ba  mov     rcx, cs:hHeap; hHeap
0x18003b4c1  mov     r8, rbx; lpMem
0x18003b4c4  xor     edx, edx; dwFlags
0x18003b4c6  call    cs:__imp_HeapFree
0x18003b4cc  mov     edi, 0Dh
0x18003b4d1  mov     ecx, edi; dwErrCode
0x18003b4d3  call    cs:__imp_SetLastError
0x18003b4d9  xor     eax, eax
0x18003b4db  test    edi, edi
0x18003b4dd  setz    al
0x18003b4e0  add     rsp, 20h
0x18003b4e4  pop     r15
0x18003b4e6  pop     r14
0x18003b4e8  pop     r12
0x18003b4ea  pop     rdi
0x18003b4eb  pop     rsi
0x18003b4ec  pop     rbp
0x18003b4ed  pop     rbx
0x18003b4ee  retn
```
