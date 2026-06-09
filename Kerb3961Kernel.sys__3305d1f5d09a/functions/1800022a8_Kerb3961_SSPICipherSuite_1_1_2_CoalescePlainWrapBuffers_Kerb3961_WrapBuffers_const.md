# Kerb3961::SSPICipherSuite<1,1,2>::CoalescePlainWrapBuffers(Kerb3961::WrapBuffers const &)

- ea: `0x1800022a8`
- end: `0x1800023d5`
- name: `?CoalescePlainWrapBuffers@?$SSPICipherSuite@$00$00$01@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z`
- size: `301`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800064e0`
- `0x180009300`
- `0x180010760`

## callees

- `0x1800022a8`
- `0x180005b1c`
- `0x180011760`
- `0x180011b40`
- `0x180012300`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,2>::CoalescePlainWrapBuffers(__int64 a1, __int64 *a2)
{
  __int64 v2; // rax
  _QWORD *v5; // rcx
  const char *v6; // rdx
  _QWORD *v7; // r9
  unsigned __int64 v8; // r8
  const char *v9; // rdx
  int v10; // ebp
  __int64 v11; // rdi
  void *v12; // r15
  char *v13; // r14
  __int64 v14; // rsi
  char *v15; // rcx
  _BYTE *v16; // rcx
  __int64 v18; // [rsp+20h] [rbp-58h] BYREF
  void *v19; // [rsp+28h] [rbp-50h]
  __int64 v20; // [rsp+30h] [rbp-48h]

  v2 = *a2;
  if ( *a2 )
  {
    if ( v2 == 1 )
    {
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
      *(_DWORD *)(a1 + 16) = 255;
    }
    else
    {
      v5 = (_QWORD *)a2[1];
      v6 = 0;
      v7 = &v5[3 * v2];
      while ( v5 != v7 )
      {
        v8 = (unsigned __int64)&v6[*v5];
        if ( v8 < (unsigned __int64)v6 )
        {
          v15 = "newTotalLength >= totalLength";
          goto LABEL_13;
        }
        if ( v8 > 0xFFFFFFFFFFFF0000uLL )
        {
          v15 = "newTotalLength <= MessageLimit";
LABEL_13:
          Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v15, v6);
          *(_QWORD *)a1 = 0;
          *(_QWORD *)(a1 + 8) = 0;
          *(_DWORD *)(a1 + 16) = -1073741675;
          return a1;
        }
        v6 += *v5;
        v5 += 3;
      }
      Kerb3961::MakeBuffer((__int64)&v18, (const struct std::nothrow_t *)v6);
      v10 = v20;
      if ( (int)v20 < 0 )
      {
        Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"result", v9);
        v16 = v19;
        *(_QWORD *)a1 = 0;
        *(_QWORD *)(a1 + 8) = 0;
        *(_DWORD *)(a1 + 16) = -1073741801;
        if ( v16 )
          Kerb3961Free(v16);
      }
      else
      {
        v11 = a2[1];
        v12 = v19;
        v13 = (char *)v19;
        v14 = v11 + 24 * *a2;
        while ( v11 != v14 )
        {
          memmove(v13, *(const void **)(v11 + 8), *(_QWORD *)v11);
          v13 += *(_QWORD *)v11;
          v11 += 24;
        }
        *(_QWORD *)a1 = v18;
        *(_DWORD *)(a1 + 16) = v10;
        *(_QWORD *)(a1 + 8) = v12;
      }
    }
  }
  else
  {
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x1800022a8  push    rbx
0x1800022aa  push    rbp
0x1800022ab  push    rsi
0x1800022ac  push    rdi
0x1800022ad  push    r14
0x1800022af  push    r15
0x1800022b1  sub     rsp, 48h
0x1800022b5  mov     rax, [rdx]
0x1800022b8  xor     edi, edi
0x1800022ba  mov     rsi, rdx
0x1800022bd  mov     rbx, rcx
0x1800022c0  test    rax, rax
0x1800022c3  jnz     short loc_1800022D4
0x1800022c5  mov     [rcx], rdi
0x1800022c8  mov     [rcx+8], rdi
0x1800022cc  mov     [rcx+10h], edi
0x1800022cf  jmp     loc_1800023C4
0x1800022d4  cmp     rax, 1
0x1800022d8  jnz     short loc_1800022ED
0x1800022da  mov     [rcx], rdi
0x1800022dd  mov     [rcx+8], rdi
0x1800022e1  mov     dword ptr [rcx+10h], 0FFh
0x1800022e8  jmp     loc_1800023C4
0x1800022ed  mov     rcx, [rsi+8]
0x1800022f1  lea     rax, [rax+rax*2]
0x1800022f5  mov     rdx, rdi
0x1800022f8  lea     r9, [rcx+rax*8]
0x1800022fc  jmp     short loc_180002319
0x1800022fe  mov     r8, [rcx]
0x180002301  add     r8, rdx
0x180002304  cmp     r8, rdx
0x180002307  jb      short loc_180002366
0x180002309  cmp     r8, 0FFFFFFFFFFFF0000h
0x180002310  ja      short loc_18000234A
0x180002312  mov     rdx, r8; char *
0x180002315  add     rcx, 18h
0x180002319  cmp     rcx, r9
0x18000231c  jnz     short loc_1800022FE
0x18000231e  lea     rcx, [rsp+78h+var_58]
0x180002323  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x180002328  mov     rbp, [rsp+78h+var_48]
0x18000232d  test    ebp, ebp
0x18000232f  js      short loc_18000239B
0x180002331  mov     rax, [rsi]
0x180002334  mov     rdi, [rsi+8]
0x180002338  mov     r15, [rsp+78h+var_50]
0x18000233d  mov     r14, r15
0x180002340  lea     rcx, [rax+rax*2]
0x180002344  lea     rsi, [rdi+rcx*8]
0x180002348  jmp     short loc_180002385
0x18000234a  lea     rcx, aNewtotallength_0; "newTotalLength <= MessageLimit"
0x180002351  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180002356  mov     [rbx], rdi
0x180002359  mov     [rbx+8], rdi
0x18000235d  mov     dword ptr [rbx+10h], 0C0000095h
0x180002364  jmp     short loc_1800023C4
0x180002366  lea     rcx, aNewtotallength; "newTotalLength >= totalLength"
0x18000236d  jmp     short loc_180002351
0x18000236f  mov     r8, [rdi]; Size
0x180002372  mov     rcx, r14; void *
0x180002375  mov     rdx, [rdi+8]; Src
0x180002379  call    memmove
0x18000237e  add     r14, [rdi]
0x180002381  add     rdi, 18h
0x180002385  cmp     rdi, rsi
0x180002388  jnz     short loc_18000236F
0x18000238a  mov     rax, [rsp+78h+var_58]
0x18000238f  mov     [rbx], rax
0x180002392  mov     [rbx+10h], ebp
0x180002395  mov     [rbx+8], r15
0x180002399  jmp     short loc_1800023C4
0x18000239b  lea     rcx, aResult; "result"
0x1800023a2  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800023a7  mov     rcx, [rsp+78h+var_50]
0x1800023ac  mov     [rbx], rdi
0x1800023af  mov     [rbx+8], rdi
0x1800023b3  mov     dword ptr [rbx+10h], 0C0000017h
0x1800023ba  test    rcx, rcx
0x1800023bd  jz      short loc_1800023C4
0x1800023bf  call    Kerb3961Free
0x1800023c4  mov     rax, rbx
0x1800023c7  add     rsp, 48h
0x1800023cb  pop     r15
0x1800023cd  pop     r14
0x1800023cf  pop     rdi
0x1800023d0  pop     rsi
0x1800023d1  pop     rbp
0x1800023d2  pop     rbx
0x1800023d3  retn
```
