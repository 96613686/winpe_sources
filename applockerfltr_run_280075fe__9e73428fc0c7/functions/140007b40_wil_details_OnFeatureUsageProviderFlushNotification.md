# wil_details_OnFeatureUsageProviderFlushNotification

- ea: `0x140007b40`
- end: `0x140007bba`
- name: `wil_details_OnFeatureUsageProviderFlushNotification`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400013f4`
- `0x140007b40`

## pseudocode

```c
unsigned __int64 __fastcall wil_details_OnFeatureUsageProviderFlushNotification(int a1)
{
  unsigned __int64 result; // rax
  __int64 *i; // rbx

  if ( a1 == 1 )
  {
    result = (unsigned int)_InterlockedExchange(&g_wil_details_featureUsageCached, 0);
    if ( (_DWORD)result )
    {
      for ( i = wil_details_featureDescriptors_a; i < wil_details_featureDescriptors_a; ++i )
      {
        if ( *i )
        {
LABEL_15:
          if ( i )
          {
            result = *(unsigned int *)i[1];
            if ( (result & 1) != 0 )
              result = (unsigned __int64)wil_details_RecordCachedUsage(*((_DWORD *)i + 6), i[1]);
            for ( i += 7; i < wil_details_featureDescriptors_a; ++i )
            {
              if ( *i )
                goto LABEL_15;
            }
          }
          return result;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140007b40  cmp     ecx, 1
0x140007b43  jnz     short locret_140007BB8
0x140007b45  mov     [rsp+arg_0], rbx
0x140007b4a  push    rdi
0x140007b4b  sub     rsp, 20h
0x140007b4f  xor     eax, eax
0x140007b51  xchg    eax, cs:g_wil_details_featureUsageCached
0x140007b57  test    eax, eax
0x140007b59  jz      short loc_140007BAE
0x140007b5b  lea     rbx, wil_details_featureDescriptors_a
0x140007b62  lea     rdi, wil_details_featureDescriptors_a
0x140007b69  jmp     short loc_140007B75
0x140007b6b  cmp     qword ptr [rbx], 0
0x140007b6f  jnz     short loc_140007BA9
0x140007b71  add     rbx, 8
0x140007b75  cmp     rbx, rdi
0x140007b78  jb      short loc_140007B6B
0x140007b7a  jmp     short loc_140007BAE
0x140007b7c  mov     rax, [rbx+8]
0x140007b80  mov     eax, [rax]
0x140007b82  test    al, 1
0x140007b84  jz      short loc_140007B92
0x140007b86  mov     rdx, [rbx+8]
0x140007b8a  mov     ecx, [rbx+18h]
0x140007b8d  call    wil_details_RecordCachedUsage
0x140007b92  add     rbx, 38h ; '8'
0x140007b96  jmp     short loc_140007BA2
0x140007b98  cmp     qword ptr [rbx], 0
0x140007b9c  jnz     short loc_140007BA9
0x140007b9e  add     rbx, 8
0x140007ba2  cmp     rbx, rdi
0x140007ba5  jb      short loc_140007B98
0x140007ba7  jmp     short loc_140007BAE
0x140007ba9  test    rbx, rbx
0x140007bac  jnz     short loc_140007B7C
0x140007bae  mov     rbx, [rsp+28h+arg_0]
0x140007bb3  add     rsp, 20h
0x140007bb7  pop     rdi
0x140007bb8  retn
```
