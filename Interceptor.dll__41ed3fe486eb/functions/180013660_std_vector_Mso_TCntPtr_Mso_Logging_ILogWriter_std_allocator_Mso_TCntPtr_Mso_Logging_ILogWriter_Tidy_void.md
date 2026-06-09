# std::vector<Mso::TCntPtr<Mso::Logging::ILogWriter>,std::allocator<Mso::TCntPtr<Mso::Logging::ILogWriter>>>::_Tidy(void)

- ea: `0x180013660`
- end: `0x180013719`
- name: `?_Tidy@?$vector@V?$TCntPtr@UILogWriter@Logging@Mso@@@Mso@@V?$allocator@V?$TCntPtr@UILogWriter@Logging@Mso@@@Mso@@@std@@@std@@AEAAXXZ`
- size: `185`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180012dd0`
- `0x180012ec0`
- `0x180012ff0`
- `0x180013080`
- `0x180013100`
- `0x1800133b0`
- `0x180013460`
- `0x1800134c0`
- `0x18001363c`
- `0x180015860`

## callees

- `0x180013660`
- `0x18002b3c0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180013712`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180013712`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800136d2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800136d2`

## pseudocode

```c
void __fastcall std::vector<Mso::TCntPtr<Mso::Logging::ILogWriter>>::_Tidy(__int64 a1)
{
  __int64 *v1; // rbx
  __int64 *v3; // rsi
  __int64 v4; // rcx
  __int64 *v5; // rcx

  v1 = *(__int64 **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(__int64 **)(a1 + 8);
    while ( v1 != v3 )
    {
      v4 = *v1;
      if ( *v1 )
      {
        *v1 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
      }
      ++v1;
    }
    v5 = *(__int64 **)a1;
    if ( ((*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFF8uLL) >= 0x1000 )
    {
      _mm_lfence();
      if ( (unsigned __int64)v5 - *(v5 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v5 = (__int64 *)*(v5 - 1);
    }
    free(v5);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x180013660  mov     [rsp+arg_0], rbx
0x180013665  mov     [rsp+arg_8], rsi
0x18001366a  push    rdi
0x18001366b  sub     rsp, 30h
0x18001366f  mov     rbx, [rcx]
0x180013672  mov     rdi, rcx
0x180013675  test    rbx, rbx
0x180013678  jz      short loc_1800136EF
0x18001367a  mov     rsi, [rcx+8]
0x18001367e  jmp     short loc_1800136A0
0x180013680  mov     rcx, [rbx]
0x180013683  test    rcx, rcx
0x180013686  jz      short loc_18001369C
0x180013688  mov     qword ptr [rbx], 0
0x18001368f  mov     rax, [rcx]
0x180013692  mov     rax, [rax+8]
0x180013696  call    cs:__guard_dispatch_icall_fptr
0x18001369c  add     rbx, 8
0x1800136a0  cmp     rbx, rsi
0x1800136a3  jnz     short loc_180013680
0x1800136a5  mov     rcx, [rdi]
0x1800136a8  mov     rax, [rdi+10h]
0x1800136ac  sub     rax, rcx
0x1800136af  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800136b3  cmp     rax, 1000h
0x1800136b9  jb      short loc_1800136D2
0x1800136bb  lfence
0x1800136be  mov     rdx, [rcx-8]
0x1800136c2  sub     rcx, rdx
0x1800136c5  lea     rax, [rcx-8]
0x1800136c9  cmp     rax, 1Fh
0x1800136cd  ja      short loc_1800136FF
0x1800136cf  mov     rcx, rdx; Block
0x1800136d2  call    cs:__imp_free
0x1800136d8  mov     qword ptr [rdi], 0
0x1800136df  mov     qword ptr [rdi+8], 0
0x1800136e7  mov     qword ptr [rdi+10h], 0
0x1800136ef  mov     rbx, [rsp+38h+arg_0]
0x1800136f4  mov     rsi, [rsp+38h+arg_8]
0x1800136f9  add     rsp, 30h
0x1800136fd  pop     rdi
0x1800136fe  retn
0x1800136ff  xor     r9d, r9d; LineNo
0x180013702  mov     [rsp+38h+Reserved], 0; Reserved
0x18001370b  xor     r8d, r8d; FileName
0x18001370e  xor     edx, edx; FunctionName
0x180013710  xor     ecx, ecx; Expression
0x180013712  call    cs:__imp__invoke_watson
```
