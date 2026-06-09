# ATL::CSid::~CSid(void)

- ea: `0x1400093b4`
- end: `0x140009479`
- name: `??1CSid@ATL@@UEAA@XZ`
- size: `197`
- prototype: `void __fastcall(ATL::CSid *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400086fc`
- `0x140009380`
- `0x140011b04`
- `0x140012d50`
- `0x140012f10`
- `0x140015140`
- `0x140015a80`

## callees

- `0x1400093b4`
- `0x140014c70`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall ATL::CSid::~CSid(ATL::CSid *this)
{
  volatile signed __int32 *v1; // rdx
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rdx
  volatile signed __int32 *v5; // rdx

  v1 = (volatile signed __int32 *)(*((_QWORD *)this + 14) - 24LL);
  *(_QWORD *)this = &ATL::CSid::`vftable';
  if ( _InterlockedDecrement(v1 + 4) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v1 + 8LL))(*(_QWORD *)v1);
  }
  v3 = (volatile signed __int32 *)(*((_QWORD *)this + 13) - 24LL);
  if ( _InterlockedDecrement(v3 + 4) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v3 + 8LL))(*(_QWORD *)v3);
  }
  v4 = (volatile signed __int32 *)(*((_QWORD *)this + 12) - 24LL);
  if ( _InterlockedDecrement(v4 + 4) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 8LL))(*(_QWORD *)v4);
  }
  v5 = (volatile signed __int32 *)(*((_QWORD *)this + 11) - 24LL);
  if ( _InterlockedDecrement(v5 + 4) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
  }
}

```

## disassembly

```asm
0x1400093b4  mov     [rsp+arg_0], rbx
0x1400093b9  push    rdi
0x1400093ba  sub     rsp, 20h
0x1400093be  mov     rdx, [rcx+70h]
0x1400093c2  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x1400093c9  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400093cd  mov     [rcx], rax
0x1400093d0  or      edi, 0FFFFFFFFh
0x1400093d3  mov     rbx, rcx
0x1400093d6  mov     eax, edi
0x1400093d8  lock xadd [rdx+10h], eax
0x1400093dd  add     eax, edi
0x1400093df  test    eax, eax
0x1400093e1  jg      short loc_1400093F6
0x1400093e3  lfence
0x1400093e6  mov     rcx, [rdx]
0x1400093e9  mov     rax, [rcx]
0x1400093ec  mov     rax, [rax+8]
0x1400093f0  call    cs:__guard_dispatch_icall_fptr
0x1400093f6  mov     rdx, [rbx+68h]
0x1400093fa  mov     eax, edi
0x1400093fc  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140009400  lock xadd [rdx+10h], eax
0x140009405  add     eax, edi
0x140009407  test    eax, eax
0x140009409  jg      short loc_14000941E
0x14000940b  lfence
0x14000940e  mov     rcx, [rdx]
0x140009411  mov     rax, [rcx]
0x140009414  mov     rax, [rax+8]
0x140009418  call    cs:__guard_dispatch_icall_fptr
0x14000941e  mov     rdx, [rbx+60h]
0x140009422  mov     eax, edi
0x140009424  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140009428  lock xadd [rdx+10h], eax
0x14000942d  add     eax, edi
0x14000942f  test    eax, eax
0x140009431  jg      short loc_140009446
0x140009433  lfence
0x140009436  mov     rcx, [rdx]
0x140009439  mov     rax, [rcx]
0x14000943c  mov     rax, [rax+8]
0x140009440  call    cs:__guard_dispatch_icall_fptr
0x140009446  mov     rdx, [rbx+58h]
0x14000944a  mov     eax, edi
0x14000944c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140009450  lock xadd [rdx+10h], eax
0x140009455  add     eax, edi
0x140009457  test    eax, eax
0x140009459  jg      short loc_14000946E
0x14000945b  lfence
0x14000945e  mov     rcx, [rdx]
0x140009461  mov     rax, [rcx]
0x140009464  mov     rax, [rax+8]
0x140009468  call    cs:__guard_dispatch_icall_fptr
0x14000946e  mov     rbx, [rsp+28h+arg_0]
0x140009473  add     rsp, 20h
0x140009477  pop     rdi
0x140009478  retn
```
