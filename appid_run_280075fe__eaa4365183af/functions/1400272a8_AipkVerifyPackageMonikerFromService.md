# AipkVerifyPackageMonikerFromService

- ea: `0x1400272a8`
- end: `0x1400273df`
- name: `AipkVerifyPackageMonikerFromService`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140028a6c`

## callees

- `0x140006c40`
- `0x1400272a8`
- `0x14002b378`
- `0x1400328b0`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400273bb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400273bb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400272d2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400272d2`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400272e7`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400272e7`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400273af`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400273af`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027386`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002739a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027386`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002739a`

## pseudocode

```c
__int64 __fastcall AipkVerifyPackageMonikerFromService(
        const void **a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  _WORD *v6; // rbx
  unsigned int v11; // edi
  _WORD *v12; // rax
  PCWSTR SourceString; // [rsp+40h] [rbp-48h] BYREF
  PCWSTR v15; // [rsp+48h] [rbp-40h] BYREF

  v6 = 0;
  SourceString = 0;
  v15 = 0;
  v11 = -2;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&AipServiceContext, 0);
  if ( *(&Binding + 1) && Binding )
  {
    v12 = (_WORD *)AiAlloc(*(unsigned __int16 *)a1 + 2LL);
    v6 = v12;
    if ( v12 )
    {
      memmove(v12, a1[1], *(unsigned __int16 *)a1);
      v6[(unsigned __int64)*(unsigned __int16 *)a1 >> 1] = 0;
      v11 = AiVerifyPackageMoniker(
              (_DWORD)Binding,
              (_DWORD)v6,
              (unsigned int)&SourceString,
              (unsigned int)&v15,
              a4,
              a5,
              a6);
      RtlInitUnicodeString(a2, SourceString);
      RtlInitUnicodeString(a3, v15);
    }
    else
    {
      v11 = -1073741801;
    }
  }
  ExReleasePushLockSharedEx(&AipServiceContext, 0);
  KeLeaveCriticalRegion();
  AiFree(v6);
  return v11;
}

```

## disassembly

```asm
0x1400272a8  push    rbx
0x1400272aa  push    rbp
0x1400272ab  push    rsi
0x1400272ac  push    rdi
0x1400272ad  push    r14
0x1400272af  push    r15
0x1400272b1  sub     rsp, 58h
0x1400272b5  xor     ebx, ebx
0x1400272b7  mov     rbp, r9
0x1400272ba  mov     [rsp+88h+SourceString], rbx
0x1400272bf  mov     r14, r8
0x1400272c2  mov     [rsp+88h+var_40], rbx
0x1400272c7  mov     r15, rdx
0x1400272ca  mov     rsi, rcx
0x1400272cd  mov     edi, 0FFFFFFFEh
0x1400272d2  call    cs:__imp_KeEnterCriticalRegion
0x1400272d9  nop     dword ptr [rax+rax+00h]
0x1400272de  xor     edx, edx
0x1400272e0  lea     rcx, AipServiceContext
0x1400272e7  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400272ee  nop     dword ptr [rax+rax+00h]
0x1400272f3  cmp     qword ptr cs:Binding+8, rbx
0x1400272fa  jz      loc_1400273A6
0x140027300  cmp     qword ptr cs:Binding, rbx
0x140027307  jz      loc_1400273A6
0x14002730d  movzx   ecx, word ptr [rsi]
0x140027310  add     rcx, 2
0x140027314  call    AiAlloc
0x140027319  mov     rbx, rax
0x14002731c  test    rax, rax
0x14002731f  jnz     short loc_140027328
0x140027321  mov     edi, 0C0000017h
0x140027326  jmp     short loc_1400273A6
0x140027328  movzx   r8d, word ptr [rsi]; Size
0x14002732c  mov     rcx, rbx; void *
0x14002732f  mov     rdx, [rsi+8]; Src
0x140027333  call    memmove
0x140027338  movzx   ecx, word ptr [rsi]
0x14002733b  lea     r9, [rsp+88h+var_40]
0x140027340  xor     eax, eax
0x140027342  shr     rcx, 1
0x140027345  lea     r8, [rsp+88h+SourceString]
0x14002734a  mov     rdx, rbx
0x14002734d  mov     [rbx+rcx*2], ax
0x140027351  mov     rax, [rsp+88h+arg_28]
0x140027359  mov     rcx, qword ptr cs:Binding
0x140027360  mov     [rsp+88h+var_58], rax
0x140027365  mov     rax, [rsp+88h+arg_20]
0x14002736d  mov     [rsp+88h+var_60], rax
0x140027372  mov     [rsp+88h+var_68], rbp
0x140027377  call    AiVerifyPackageMoniker
0x14002737c  mov     rdx, [rsp+88h+SourceString]; SourceString
0x140027381  mov     rcx, r15; DestinationString
0x140027384  mov     edi, eax
0x140027386  call    cs:__imp_RtlInitUnicodeString
0x14002738d  nop     dword ptr [rax+rax+00h]
0x140027392  mov     rdx, [rsp+88h+var_40]; SourceString
0x140027397  mov     rcx, r14; DestinationString
0x14002739a  call    cs:__imp_RtlInitUnicodeString
0x1400273a1  nop     dword ptr [rax+rax+00h]
0x1400273a6  xor     edx, edx
0x1400273a8  lea     rcx, AipServiceContext
0x1400273af  call    cs:__imp_ExReleasePushLockSharedEx
0x1400273b6  nop     dword ptr [rax+rax+00h]
0x1400273bb  call    cs:__imp_KeLeaveCriticalRegion
0x1400273c2  nop     dword ptr [rax+rax+00h]
0x1400273c7  mov     rcx, rbx
0x1400273ca  call    AiFree
0x1400273cf  mov     eax, edi
0x1400273d1  add     rsp, 58h
0x1400273d5  pop     r15
0x1400273d7  pop     r14
0x1400273d9  pop     rdi
0x1400273da  pop     rsi
0x1400273db  pop     rbp
0x1400273dc  pop     rbx
0x1400273dd  retn
```
