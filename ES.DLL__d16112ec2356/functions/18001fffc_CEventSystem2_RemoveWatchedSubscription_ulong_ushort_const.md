# CEventSystem2::RemoveWatchedSubscription(ulong,ushort const *)

- ea: `0x18001fffc`
- end: `0x180020144`
- name: `?RemoveWatchedSubscription@CEventSystem2@@AEAAXKPEBG@Z`
- size: `328`
- prototype: `void __fastcall(CEventSystem2 *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bf40`
- `0x180011a30`

## callees

- `0x18001fffc`
- `0x18002014c`
- `0x180020284`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800200c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002010c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800200c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002010c`

## pseudocode

```c
void __fastcall CEventSystem2::RemoveWatchedSubscription(struct _RTL_CRITICAL_SECTION *this, unsigned int a2, char *a3)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r9
  __int64 *i; // rax
  __int64 v8; // r14
  _QWORD *v9; // rdi
  const OLECHAR *v10; // rax
  _QWORD *v11; // r9
  const OLECHAR *v12; // rcx
  char *v13; // r8
  unsigned __int16 v14; // dx
  int v15; // ecx
  OLECHAR *v16; // rbx

  DebugInfo = this[2].DebugInfo;
  if ( DebugInfo )
  {
    for ( i = (__int64 *)*((_QWORD *)&DebugInfo->Type + (a2 >> 4) % this[2].LockCount); i; i = (__int64 *)*i )
    {
      if ( *((_DWORD *)i + 3) == a2 )
      {
        v8 = i[2];
        v9 = *(_QWORD **)(v8 + 24);
        while ( v9 )
        {
          v10 = (const OLECHAR *)v9[2];
          v11 = (_QWORD *)*v9;
          if ( *((int *)v10 - 3) < 0 )
            v10 = &dword_180053104;
          else
            _InterlockedIncrement((volatile signed __int32 *)v10 - 3);
          if ( a3 )
          {
            v12 = v10;
            v13 = (char *)(a3 - (char *)v10);
            while ( 1 )
            {
              v14 = *v12;
              if ( *v12 != *(_WORD *)&v13[(_QWORD)v12] )
                break;
              ++v12;
              if ( !v14 )
              {
                v15 = 0;
                goto LABEL_15;
              }
            }
            v15 = v14 < *(_WORD *)&v13[(_QWORD)v12] ? -1 : 1;
          }
          else
          {
            v15 = *((_DWORD *)v10 - 2) != 0;
          }
LABEL_15:
          v16 = (OLECHAR *)(v10 - 6);
          if ( !v15 )
          {
            CList<CString,CString>::RemoveAt(v8 + 24, v9, &qword_1800530F8, v11);
            if ( !*(_DWORD *)(v8 + 40) )
              CEventSystem2::RemoveWatchedProcess(this, a2, (struct CEventSystem2::TransientSubscriberProcessData *)v8);
            if ( v16 != (OLECHAR *)&qword_1800530F8
              && _InterlockedExchangeAdd((volatile signed __int32 *)v16, 0xFFFFFFFF) == 1 )
            {
              CoTaskMemFree(v16);
            }
            return;
          }
          v9 = v11;
          if ( v16 != (OLECHAR *)&qword_1800530F8
            && _InterlockedExchangeAdd((volatile signed __int32 *)v16, 0xFFFFFFFF) == 1 )
          {
            CoTaskMemFree(v16);
          }
        }
        return;
      }
    }
  }
}

```

## disassembly

```asm
0x18001fffc  push    rbx
0x18001fffe  push    rbp
0x18001ffff  push    rsi
0x180020000  push    rdi
0x180020001  push    r12
0x180020003  push    r14
0x180020005  push    r15
0x180020007  sub     rsp, 20h
0x18002000b  mov     r9, [rcx+50h]
0x18002000f  mov     r12, r8
0x180020012  mov     esi, edx
0x180020014  mov     rbp, rcx
0x180020017  test    r9, r9
0x18002001a  jz      loc_180020112
0x180020020  mov     eax, edx
0x180020022  xor     edx, edx
0x180020024  shr     eax, 4
0x180020027  div     dword ptr [rcx+58h]
0x18002002a  mov     rax, [r9+rdx*8]
0x18002002e  test    rax, rax
0x180020031  jz      loc_180020112
0x180020037  cmp     [rax+0Ch], esi
0x18002003a  jz      short loc_180020041
0x18002003c  mov     rax, [rax]
0x18002003f  jmp     short loc_18002002E
0x180020041  mov     r14, [rax+10h]
0x180020045  mov     rdi, [r14+18h]
0x180020049  lea     r8, qword_1800530F8
0x180020050  test    rdi, rdi
0x180020053  jz      loc_180020112
0x180020059  mov     rax, [rdi+10h]
0x18002005d  mov     r9, [rdi]
0x180020060  cmp     dword ptr [rax-0Ch], 0
0x180020064  jl      loc_18002012B
0x18002006a  lock inc dword ptr [rax-0Ch]
0x18002006e  test    r12, r12
0x180020071  jz      loc_180020137
0x180020077  mov     r8, r12
0x18002007a  mov     rcx, rax
0x18002007d  sub     r8, rax
0x180020080  movzx   edx, word ptr [rcx]
0x180020083  cmp     dx, [rcx+r8]
0x180020088  jnz     loc_180020121
0x18002008e  add     rcx, 2
0x180020092  test    dx, dx
0x180020095  jnz     short loc_180020080
0x180020097  xor     ecx, ecx
0x180020099  lea     r8, qword_1800530F8
0x1800200a0  mov     rdx, 0FFFFFFFFFFFFFFF4h
0x1800200a7  lea     rbx, [rdx+rax]
0x1800200ab  test    ecx, ecx
0x1800200ad  jz      short loc_1800200D1
0x1800200af  mov     rdi, r9
0x1800200b2  cmp     rbx, r8
0x1800200b5  jz      short loc_180020050
0x1800200b7  or      eax, 0FFFFFFFFh
0x1800200ba  lock xadd [rbx], eax
0x1800200be  cmp     eax, 1
0x1800200c1  jnz     short loc_180020050
0x1800200c3  mov     rcx, rbx; pv
0x1800200c6  call    cs:__imp_CoTaskMemFree
0x1800200cc  jmp     loc_180020049
0x1800200d1  mov     rdx, rdi
0x1800200d4  lea     rcx, [r14+18h]
0x1800200d8  call    ?RemoveAt@?$CList@VCString@@V1@@@QEAAXPEAU__POSITION@@@Z; CList<CString,CString>::RemoveAt(__POSITION *)
0x1800200dd  cmp     dword ptr [r14+28h], 0
0x1800200e2  jnz     short loc_1800200F1
0x1800200e4  mov     r8, r14; struct CEventSystem2::TransientSubscriberProcessData *
0x1800200e7  mov     edx, esi; unsigned int
0x1800200e9  mov     rcx, rbp; this
0x1800200ec  call    ?RemoveWatchedProcess@CEventSystem2@@AEAAXKPEAUTransientSubscriberProcessData@1@@Z; CEventSystem2::RemoveWatchedProcess(ulong,CEventSystem2::TransientSubscriberProcessData *)
0x1800200f1  lea     rax, qword_1800530F8
0x1800200f8  cmp     rbx, rax
0x1800200fb  jz      short loc_180020112
0x1800200fd  or      eax, 0FFFFFFFFh
0x180020100  lock xadd [rbx], eax
0x180020104  cmp     eax, 1
0x180020107  jnz     short loc_180020112
0x180020109  mov     rcx, rbx; pv
0x18002010c  call    cs:__imp_CoTaskMemFree
0x180020112  add     rsp, 20h
0x180020116  pop     r15
0x180020118  pop     r14
0x18002011a  pop     r12
0x18002011c  pop     rdi
0x18002011d  pop     rsi
0x18002011e  pop     rbp
0x18002011f  pop     rbx
0x180020120  retn
0x180020121  sbb     ecx, ecx
0x180020123  or      ecx, 1
0x180020126  jmp     loc_180020099
0x18002012b  lea     rax, dword_180053104
0x180020132  jmp     loc_18002006E
0x180020137  xor     ecx, ecx
0x180020139  cmp     [rax-8], ecx
0x18002013c  setnz   cl
0x18002013f  jmp     loc_1800200A0
```
