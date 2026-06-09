# WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::Decrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1 *)

- ea: `0x180022130`
- end: `0x1800221c0`
- name: `?Decrypt@?$CEncryption@$0A@V?$CCipherFeistel64@$0BC@$0GD@$0EK@$0OP@$0BE@$0OE@$0CF@$0MC@$0BO@$0FO@$0HK@$0EN@$0BJ@$0HG@$0PI@$0OK@$0BG@$0PH@$0CF@$0JN@$00$03$0N@$0BE@$07$0HP@$07$0NI@$0L@$0BN@$0FB@$0EK@$09$0OH@$0HF@$0BM@$01$0NF@$0ND@$0FG@@WarbirdCrypto@@V?$CHashFunctionSCP@$01$02$0A@$0?BMINLIEJLPHNNHJC@@2@UENCRYPTED_SEGMENT_DATA_CONST_1@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_1@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_1@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_1@2@@Z`
- size: `144`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b900`
- `0x18001e410`

## callees

- `0x180022130`
- `0x1800236a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022197`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022197`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022151`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022151`

## pseudocode

```c
__int64 WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::Decrypt()
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  int v3; // ebx

  if ( !WarbirdRuntime::g_EncryptedSegmentConstData_3 )
    return 0;
  EnterCriticalSection(&WarbirdRuntime::g_encryptionLock);
  if ( WarbirdRuntime::g_EncryptedSegmentReadWriteData_3 )
  {
    v3 = 0;
    if ( WarbirdRuntime::g_EncryptedSegmentReadWriteData_3 != -1 )
      ++WarbirdRuntime::g_EncryptedSegmentReadWriteData_3;
  }
  else
  {
    v3 = WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::DoCrypt(
           v2,
           v1,
           0);
    if ( v3 >= 0 )
      WarbirdRuntime::g_EncryptedSegmentReadWriteData_3 = 1;
  }
  LeaveCriticalSection(&WarbirdRuntime::g_encryptionLock);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180022130  sub     rsp, 28h
0x180022134  test    byte ptr cs:?g_EncryptedSegmentConstData_3@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_1@1@A, 1; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1 WarbirdRuntime::g_EncryptedSegmentConstData_3
0x18002213b  jnz     short loc_180022145
0x18002213d  xor     eax, eax
0x18002213f  add     rsp, 28h
0x180022143  retn
0x180022145  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x18002214c  mov     [rsp+28h+var_8], rbx
0x180022151  call    cs:__imp_EnterCriticalSection
0x180022158  nop     dword ptr [rax+rax+00h]
0x18002215d  mov     eax, cs:?g_EncryptedSegmentReadWriteData_3@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_1@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1 WarbirdRuntime::g_EncryptedSegmentReadWriteData_3
0x180022163  test    eax, eax
0x180022165  jnz     short loc_180022181
0x180022167  xor     r8d, r8d
0x18002216a  call    ?DoCrypt@?$CEncryption@$0A@V?$CCipherFeistel64@$0BC@$0GD@$0EK@$0OP@$0BE@$0OE@$0CF@$0MC@$0BO@$0FO@$0HK@$0EN@$0BJ@$0HG@$0PI@$0OK@$0BG@$0PH@$0CF@$0JN@$00$03$0N@$0BE@$07$0HP@$07$0NI@$0L@$0BN@$0FB@$0EK@$09$0OH@$0HF@$0BM@$01$0NF@$0ND@$0FG@@WarbirdCrypto@@V?$CHashFunctionSCP@$01$02$0A@$0?BMINLIEJLPHNNHJC@@2@UENCRYPTED_SEGMENT_DATA_CONST_1@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_1@5@@WarbirdRuntime@@CAJPEAUENCRYPTED_SEGMENT_DATA_CONST_1@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_1@2@H@Z; WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::DoCrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1 *,int)
0x18002216f  mov     ebx, eax
0x180022171  test    eax, eax
0x180022173  js      short loc_180022190
0x180022175  mov     cs:?g_EncryptedSegmentReadWriteData_3@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_1@1@A, 1; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1 WarbirdRuntime::g_EncryptedSegmentReadWriteData_3
0x18002217f  jmp     short loc_180022190
0x180022181  xor     ebx, ebx
0x180022183  cmp     eax, 0FFFFFFFFh
0x180022186  jz      short loc_180022190
0x180022188  inc     eax
0x18002218a  mov     cs:?g_EncryptedSegmentReadWriteData_3@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_1@1@A, eax; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1 WarbirdRuntime::g_EncryptedSegmentReadWriteData_3
0x180022190  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x180022197  call    cs:__imp_LeaveCriticalSection
0x18002219e  nop     dword ptr [rax+rax+00h]
0x1800221a3  mov     eax, ebx
0x1800221a5  mov     rbx, [rsp+28h+var_8]
0x1800221aa  add     rsp, 28h
0x1800221ae  retn
```
