# CreateEmptySmartlockerPolicy(_POLICY *)

- ea: `0x14000512c`
- end: `0x14000518d`
- name: `?CreateEmptySmartlockerPolicy@@YAKPEAU_POLICY@@@Z`
- size: `97`
- prototype: `unsigned int __fastcall(struct _POLICY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000458c`

## callees

- `0x140002938`
- `0x14000512c`
- `0x140008d30`
- `0x140013acf`

## pseudocode

```c
unsigned int __fastcall CreateEmptySmartlockerPolicy(struct _POLICY *a1)
{
  void *v2; // rax
  unsigned int result; // eax

  *((_DWORD *)a1 + 9) = 1;
  v2 = (void *)AiAlloc(40);
  *((_QWORD *)a1 + 5) = v2;
  if ( !v2 )
    return 8;
  memset_0(v2, 0, 40LL * *((unsigned int *)a1 + 9));
  result = AddLowboxAceToPolicy(*((struct _POLICY_RULE **)a1 + 5));
  if ( !result )
  {
    *((_DWORD *)a1 + 2) = 0;
    *((_DWORD *)a1 + 8) = 1;
    *((_DWORD *)a1 + 3) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x14000512c  push    rbx
0x14000512e  sub     rsp, 20h
0x140005132  mov     rbx, rcx
0x140005135  mov     dword ptr [rcx+24h], 1
0x14000513c  mov     ecx, 28h ; '('
0x140005141  call    AiAlloc
0x140005146  mov     [rbx+28h], rax
0x14000514a  mov     rcx, rax; void *
0x14000514d  test    rax, rax
0x140005150  jnz     short loc_140005157
0x140005152  lea     eax, [rcx+8]
0x140005155  jmp     short loc_140005187
0x140005157  mov     eax, [rbx+24h]
0x14000515a  xor     edx, edx; Val
0x14000515c  lea     r8, [rax+rax*4]
0x140005160  shl     r8, 3; Size
0x140005164  call    memset_0
0x140005169  mov     rcx, [rbx+28h]; struct _POLICY_RULE *
0x14000516d  call    ?AddLowboxAceToPolicy@@YAKPEAU_POLICY_RULE@@@Z; AddLowboxAceToPolicy(_POLICY_RULE *)
0x140005172  test    eax, eax
0x140005174  jnz     short loc_140005187
0x140005176  mov     [rbx+8], eax
0x140005179  mov     dword ptr [rbx+20h], 1
0x140005180  mov     dword ptr [rbx+0Ch], 1
0x140005187  add     rsp, 20h
0x14000518b  pop     rbx
0x14000518c  retn
```
