# COWSMemmgr::InitMemmgrForThread(void)

- ea: `0x1800859c0`
- end: `0x180085bb8`
- name: `?InitMemmgrForThread@COWSMemmgr@@SAPEAVCOWSTlsHeapData@@XZ`
- size: `504`
- prototype: `struct COWSTlsHeapData *(void)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800db260`

## callees

- `0x180084d74`
- `0x1800850e0`
- `0x1800851e0`
- `0x1800859c0`
- `0x180086194`
- `0x180086284`
- `0x1800c34b8`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x180085adb`
- `KERNEL32!DebugBreak` at `0x180085adb`
- `KERNEL32!TlsSetValue` at `0x1800859e1`
- `KERNEL32!TlsSetValue` at `0x180085b84`
- `KERNEL32!TlsSetValue` at `0x1800859e1`
- `KERNEL32!TlsSetValue` at `0x180085b84`
- `KERNEL32!GetCurrentThreadId` at `0x180085ae6`
- `KERNEL32!GetCurrentThreadId` at `0x180085ae6`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180085a6c`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180085b2c`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180085a6c`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180085b2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct COWSTlsHeapData *COWSMemmgr::InitMemmgrForThread(void)
{
  char *v0; // rbx
  COWSMemmgr *v1; // rcx
  char v2; // si
  __int64 v3; // rdx
  __int64 v4; // rcx
  _DWORD *v5; // rax
  _DWORD *v6; // rdi
  char *v7; // rcx
  int v8; // ecx
  int v9; // eax
  struct COWSHeap *v10; // rax
  int v12; // [rsp+60h] [rbp+8h] BYREF
  struct COWSHeap *v13; // [rsp+68h] [rbp+10h] BYREF
  char *v14; // [rsp+70h] [rbp+18h]

  v13 = 0;
  v0 = 0;
  TlsSetValue(dword_1802AF500, 0);
  v1 = qword_1802B0010;
  if ( !qword_1802B0010 )
  {
    sub_180084D74();
    v1 = qword_1802B0010;
  }
  if ( (unsigned int)COWSMemmgr::AcquireLocalHeap(v1, &v13) )
  {
    if ( dword_1802B0018 )
    {
      v12 = 0;
      v2 = 0;
      if ( qword_1802B0010 )
        v0 = *(char **)qword_1802B0010;
      v3 = 56;
      if ( v0 )
      {
        if ( (v0[16] & 0x20) != 0 )
        {
          v2 = 1;
          v3 = 96;
        }
        v4 = *(_QWORD *)v0;
        v12 = v3;
        v5 = (_DWORD *)(*(__int64 (__fastcall **)(__int64, __int64, int *, _QWORD))(*(_QWORD *)v4 + 40LL))(
                         v4,
                         v3,
                         &v12,
                         0);
      }
      else
      {
        v5 = malloc(0x38u);
      }
      v6 = v5;
      if ( !v5 )
        sub_1800C34B8();
      if ( v2 )
      {
        if ( v0[16] < 0 )
          sub_180086194(v0);
        v7 = *(char **)qword_1802B0010;
        if ( *(_QWORD *)qword_1802B0010 && v7 != v0 && v7[16] < 0 )
          sub_180086194(v7);
        v8 = *((_DWORD *)v0 + 3);
        if ( (v0[16] & 2) != 0 )
        {
          v9 = _InterlockedIncrement((volatile signed __int32 *)v0 + 2);
        }
        else
        {
          v9 = *((_DWORD *)v0 + 2) + 1;
          *((_DWORD *)v0 + 2) = v9;
        }
        if ( v8 && v8 == v9 )
          DebugBreak();
        *v6 = *((_DWORD *)v0 + 2);
        v6[1] = GetCurrentThreadId();
        *((_QWORD *)v6 + 1) = "(unknown file)";
        v6[4] = -1;
        *((_QWORD *)v6 + 3) = 48;
        v6[8] = v12;
        sub_180086284(v0, v12);
        v6 += 10;
      }
      *(_QWORD *)v6 = v0;
      v0 = (char *)(v6 + 2);
    }
    else
    {
      v0 = (char *)malloc(0x30u);
    }
    v14 = v0;
    v10 = v13;
    if ( v0 )
    {
      *(_QWORD *)v0 = 0x544C534865617021LL;
      *((_QWORD *)v0 + 1) = v10;
      *((_QWORD *)v0 + 2) = v10;
      *((_DWORD *)v0 + 6) = 0;
      *((_DWORD *)v0 + 7) = 1;
      *((_DWORD *)v0 + 8) = 0;
      *((_DWORD *)v0 + 9) = 0;
      *((_DWORD *)v0 + 10) = 0;
      TlsSetValue(dword_1802AF500, v0);
      return (struct COWSTlsHeapData *)v0;
    }
  }
  else
  {
    v10 = v13;
  }
  if ( v10 )
    COWSMemmgr::ReleaseLocalHeap(qword_1802B0010, &v13);
  return (struct COWSTlsHeapData *)v0;
}

```

## disassembly

```asm
0x1800859c0  push    rbx
0x1800859c2  push    rsi
0x1800859c3  push    rdi
0x1800859c4  sub     rsp, 40h
0x1800859c8  mov     [rsp+58h+var_28], 0FFFFFFFFFFFFFFFEh
0x1800859d1  and     [rsp+58h+arg_8], 0
0x1800859d7  xor     ebx, ebx
0x1800859d9  xor     edx, edx; lpTlsValue
0x1800859db  mov     ecx, cs:dword_1802AF500; dwTlsIndex
0x1800859e1  call    cs:TlsSetValue
0x1800859e7  mov     rcx, cs:qword_1802B0010
0x1800859ee  test    rcx, rcx
0x1800859f1  jnz     short loc_1800859FF
0x1800859f3  call    sub_180084D74
0x1800859f8  mov     rcx, cs:qword_1802B0010; this
0x1800859ff  lea     rdx, [rsp+58h+arg_8]; struct COWSHeap **
0x180085a04  call    ?AcquireLocalHeap@COWSMemmgr@@QEAAHAEAPEAVCOWSHeap@@@Z; COWSMemmgr::AcquireLocalHeap(COWSHeap * &)
0x180085a09  test    eax, eax
0x180085a0b  jz      loc_180085B8C
0x180085a11  cmp     cs:dword_1802B0018, ebx
0x180085a17  jz      loc_180085B27
0x180085a1d  and     [rsp+58h+arg_0], ebx
0x180085a21  xor     sil, sil
0x180085a24  mov     rax, cs:qword_1802B0010
0x180085a2b  test    rax, rax
0x180085a2e  jz      short loc_180085A33
0x180085a30  mov     rbx, [rax]
0x180085a33  mov     edx, 38h ; '8'
0x180085a38  test    rbx, rbx
0x180085a3b  jz      short loc_180085A69
0x180085a3d  test    byte ptr [rbx+10h], 20h
0x180085a41  jz      short loc_180085A4B
0x180085a43  mov     sil, 1
0x180085a46  mov     edx, 60h ; '`'
0x180085a4b  mov     rcx, [rbx]
0x180085a4e  mov     [rsp+58h+arg_0], edx
0x180085a52  mov     rax, [rcx]
0x180085a55  xor     r9d, r9d
0x180085a58  lea     r8, [rsp+58h+arg_0]
0x180085a5d  mov     rax, [rax+28h]
0x180085a61  call    cs:__guard_dispatch_icall_fptr
0x180085a67  jmp     short loc_180085A72
0x180085a69  mov     rcx, rdx; Size
0x180085a6c  call    cs:malloc
0x180085a72  mov     rdi, rax
0x180085a75  test    rax, rax
0x180085a78  jz      loc_180085BB2
0x180085a7e  test    sil, sil
0x180085a81  jz      loc_180085B1E
0x180085a87  test    byte ptr [rbx+10h], 80h
0x180085a8b  jz      short loc_180085A95
0x180085a8d  mov     rcx, rbx
0x180085a90  call    sub_180086194
0x180085a95  mov     rax, cs:qword_1802B0010
0x180085a9c  mov     rcx, [rax]
0x180085a9f  test    rcx, rcx
0x180085aa2  jz      short loc_180085AB4
0x180085aa4  cmp     rcx, rbx
0x180085aa7  jz      short loc_180085AB4
0x180085aa9  test    byte ptr [rcx+10h], 80h
0x180085aad  jz      short loc_180085AB4
0x180085aaf  call    sub_180086194
0x180085ab4  mov     ecx, [rbx+0Ch]
0x180085ab7  test    byte ptr [rbx+10h], 2
0x180085abb  jz      short loc_180085ACB
0x180085abd  mov     eax, 1
0x180085ac2  lock xadd [rbx+8], eax
0x180085ac7  inc     eax
0x180085ac9  jmp     short loc_180085AD3
0x180085acb  mov     eax, [rbx+8]
0x180085ace  inc     eax
0x180085ad0  mov     [rbx+8], eax
0x180085ad3  test    ecx, ecx
0x180085ad5  jz      short loc_180085AE1
0x180085ad7  cmp     ecx, eax
0x180085ad9  jnz     short loc_180085AE1
0x180085adb  call    cs:DebugBreak
0x180085ae1  mov     eax, [rbx+8]
0x180085ae4  mov     [rdi], eax
0x180085ae6  call    cs:GetCurrentThreadId
0x180085aec  mov     [rdi+4], eax
0x180085aef  lea     rax, aUnknownFile; "(unknown file)"
0x180085af6  mov     [rdi+8], rax
0x180085afa  or      dword ptr [rdi+10h], 0FFFFFFFFh
0x180085afe  mov     qword ptr [rdi+18h], 30h ; '0'
0x180085b06  mov     eax, [rsp+58h+arg_0]
0x180085b0a  mov     [rdi+20h], eax
0x180085b0d  movsxd  rdx, [rsp+58h+arg_0]
0x180085b12  mov     rcx, rbx
0x180085b15  call    sub_180086284
0x180085b1a  add     rdi, 28h ; '('
0x180085b1e  mov     [rdi], rbx
0x180085b21  lea     rbx, [rdi+8]
0x180085b25  jmp     short loc_180085B35
0x180085b27  mov     ecx, 30h ; '0'; Size
0x180085b2c  call    cs:malloc
0x180085b32  mov     rbx, rax
0x180085b35  mov     [rsp+58h+arg_10], rbx
0x180085b3a  mov     rax, [rsp+58h+arg_8]
0x180085b3f  test    rbx, rbx
0x180085b42  jz      short loc_180085B76
0x180085b44  mov     rcx, 544C534865617021h
0x180085b4e  mov     [rbx], rcx
0x180085b51  mov     [rbx+8], rax
0x180085b55  mov     [rbx+10h], rax
0x180085b59  and     dword ptr [rbx+18h], 0
0x180085b5d  mov     dword ptr [rbx+1Ch], 1
0x180085b64  mov     dword ptr [rbx+20h], 0
0x180085b6b  mov     dword ptr [rbx+24h], 0
0x180085b72  and     dword ptr [rbx+28h], 0
0x180085b76  test    rbx, rbx
0x180085b79  jz      short loc_180085B91
0x180085b7b  mov     rdx, rbx; lpTlsValue
0x180085b7e  mov     ecx, cs:dword_1802AF500; dwTlsIndex
0x180085b84  call    cs:TlsSetValue
0x180085b8a  jmp     short loc_180085BA7
0x180085b8c  mov     rax, [rsp+58h+arg_8]
0x180085b91  test    rax, rax
0x180085b94  jz      short loc_180085BA7
0x180085b96  lea     rdx, [rsp+58h+arg_8]; struct COWSHeap **
0x180085b9b  mov     rcx, cs:qword_1802B0010; this
0x180085ba2  call    ?ReleaseLocalHeap@COWSMemmgr@@QEAAXAEAPEAVCOWSHeap@@@Z; COWSMemmgr::ReleaseLocalHeap(COWSHeap * &)
0x180085ba7  mov     rax, rbx
0x180085baa  add     rsp, 40h
0x180085bae  pop     rdi
0x180085baf  pop     rsi
0x180085bb0  pop     rbx
0x180085bb1  retn
0x180085bb2  call    sub_1800C34B8
```
