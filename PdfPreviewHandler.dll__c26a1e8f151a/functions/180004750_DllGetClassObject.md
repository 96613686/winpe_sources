# DllGetClassObject

- ea: `0x180004750`
- end: `0x180004819`
- name: `DllGetClassObject`
- size: `201`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004750`
- `0x180004930`
- `0x180004ad0`
- `0x180004ae0`
- `0x180004c2a`
- `0x1800113f0`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int v4; // esi
  __int64 v6; // r14
  __int64 v7; // r15
  unsigned __int64 v8; // rcx
  __int64 *v9; // r15
  HRESULT result; // eax
  __int64 v11; // r9
  __int64 v12; // [rsp+0h] [rbp-68h] BYREF
  int v13; // [rsp+34h] [rbp-34h] BYREF
  __int64 v14; // [rsp+38h] [rbp-30h]

  v4 = (int)riid;
  v6 = sub_180004930();
  *ppv = 0;
  v7 = sub_180004AD0(v6);
  v8 = sub_180004AE0(v6);
  v9 = (__int64 *)(v7 + 8);
  result = -2147221231;
  while ( (unsigned __int64)v9 < v8 )
  {
    v11 = *v9;
    if ( *v9
      && _mm_movemask_epi8(
           _mm_cmpeq_epi8(
             _mm_loadu_si128((const __m128i *)*(_QWORD *)(v11 + 8)),
             _mm_loadu_si128((const __m128i *)rclsid))) == 0xFFFF )
    {
      v13 = 1;
      result = sub_180004C2A(v6, (unsigned int)&v13, v4, v11, (__int64)ppv);
      break;
    }
    ++v9;
  }
  if ( _security_cookie != ((unsigned __int64)&v12 ^ v14) )
    JUMPOUT(0x180004818LL);
  return result;
}

```

## disassembly

```asm
0x180004750  push    r15
0x180004752  push    r14
0x180004754  push    rsi
0x180004755  push    rdi
0x180004756  push    rbx
0x180004757  sub     rsp, 40h
0x18000475b  mov     rdi, r8
0x18000475e  mov     rsi, rdx
0x180004761  mov     rbx, rcx
0x180004764  mov     rax, cs:__security_cookie
0x18000476b  xor     rax, rsp
0x18000476e  mov     [rsp+68h+var_30], rax
0x180004773  call    sub_180004930
0x180004778  mov     r14, rax
0x18000477b  mov     qword ptr [rdi], 0
0x180004782  mov     rcx, rax
0x180004785  call    sub_180004AD0
0x18000478a  mov     r15, rax
0x18000478d  mov     rcx, r14
0x180004790  call    sub_180004AE0
0x180004795  mov     rcx, rax
0x180004798  add     r15, 8
0x18000479c  mov     eax, 80040111h
0x1800047a1  jmp     short loc_1800047A7
0x1800047a3  add     r15, 8
0x1800047a7  cmp     r15, rcx
0x1800047aa  jnb     short loc_1800047EB
0x1800047ac  mov     r9, [r15]
0x1800047af  test    r9, r9
0x1800047b2  jz      short loc_1800047A3
0x1800047b4  mov     rdx, [r9+8]
0x1800047b8  movdqu  xmm0, xmmword ptr [rbx]
0x1800047bc  movdqu  xmm1, xmmword ptr [rdx]
0x1800047c0  pcmpeqb xmm1, xmm0
0x1800047c4  pmovmskb edx, xmm1
0x1800047c8  cmp     edx, 0FFFFh
0x1800047ce  jnz     short loc_1800047A3
0x1800047d0  lea     rdx, [rsp+68h+var_34]
0x1800047d5  mov     dword ptr [rdx], 1
0x1800047db  mov     [rsp+68h+var_48], rdi
0x1800047e0  mov     rcx, r14
0x1800047e3  mov     r8, rsi
0x1800047e6  call    sub_180004C2A
0x1800047eb  mov     rcx, [rsp+68h+var_30]
0x1800047f0  xor     rcx, rsp
0x1800047f3  mov     rdx, cs:__security_cookie
0x1800047fa  cmp     rdx, rcx
0x1800047fd  jnz     short loc_18000480B
0x1800047ff  add     rsp, 40h
0x180004803  pop     rbx
0x180004804  pop     rdi
0x180004805  pop     rsi
0x180004806  pop     r14
0x180004808  pop     r15
0x18000480a  retn
0x18000480b  mov     rcx, [rsp+68h+var_30]
0x180004810  xor     rcx, rsp; StackCookie
0x180004813  call    __security_check_cookie
```
